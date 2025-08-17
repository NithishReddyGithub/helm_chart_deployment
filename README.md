# 🚀 Helm Deployment: my-profile  

## 📌 Task  
Package the Kubernetes deployment into a **Helm chart** and deploy it.  
Include parameters for customization such as **replicas** and **image tags**.  

## ✅ Outcome  
- `helm-chart.tgz` (packaged Helm chart)  
- `values.yaml` (customizable values for deployment)  
- `helm-deployment-logs.txt` (logs of Helm deployment)  

---

## 📂 Files  

- [helm-chart.tgz](https://github.com/NithishReddyGithub/helm_chart_deployment/blob/main/my-profile-0.1.0.tgz)  
- [values.yaml](https://github.com/NithishReddyGithub/helm_chart_deployment/blob/main/my-profile/values.yaml)  
- [helm-deployment-logs.txt](https://github.com/NithishReddyGithub/helm_chart_deployment/blob/main/helm-deployment.log)  

---

## 🔧 Helm Chart Structure  

```bash
my-profile/
  ├── charts/
  ├── templates/
  │   ├── deployment.yaml
  │   ├── service.yaml
  │   └── _helpers.tpl
  ├── Chart.yaml
  └── values.yaml
```

---

## ⚙️ Customization (via `values.yaml`)

Example parameters:

```yaml
replicaCount: 2

image:
  repository: <acr_name>.azurecr.io/my-sample-app
  tag: latest
  pullPolicy: IfNotPresent
```

---

## 📦 Package the Helm Chart

```bash
helm package my-profile/
```
This generates:
```perl
my-profile-<version>.tgz
```

---

## 🚀 Deploy with Helm

```bash
helm install my-profile . -f values.yaml -n <namespace> --create-namespace
```

---

## ✅ Verify Deployment

```bash
helm list -n <namespace>
kubectl get pods -n <namespace>
```

---

## 📂 Logs  
  
- **kubectl get pods Output**: [kubectl-get-pods.txt](https://github.com/NithishReddyGithub/kubernetes_deployment/blob/main/get-pods.txt)  
- **kubectl describe pod Output**: [kubectl-describe-pod.txt](https://github.com/NithishReddyGithub/kubernetes_deployment/blob/main/describe-pod.txt)  

### 📸 Screenshots  
- Screenshot: ![Successful `Helm Deploy & kubectl get pods` output](./get-pods.png) 
