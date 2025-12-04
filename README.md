# Kubernetes Deployment Project (DevOps Portfolio)

This repository contains a complete Kubernetes deployment setup demonstrating essential DevOps and Kubernetes skills required in professional environments.  
The project includes Deployment, Service, Ingress, ConfigMap, Secret, and Horizontal Pod Autoscaler (HPA).

---

## 📁 Files Included

| File | Purpose |
|------|---------|
| `deployment.yaml` | Deploys the application using replicas |
| `service.yaml` | Exposes the application using NodePort |
| `ingress.yaml` | Provides external route to the service |
| `hpa.yaml` | Enables CPU-based autoscaling |
| `configmap.yaml` | Stores environment configuration |
| `secret.yaml` | Stores sensitive data (base64 encoded) |

---

## 🚀 How to Deploy the Application

### 1️⃣ Apply Deployment
```sh
kubectl apply -f deployment.yaml
```
###2️⃣ Apply Service
```sh
kubectl apply -f service.yaml
```
###3️⃣ Apply ConfigMap & Secret
```sh
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
```
###4️⃣ Apply Ingress
```sh
kubectl apply -f ingress.yaml
```
###5️⃣ Apply Autoscaling (HPA)
```sh
kubectl apply -f hpa.yaml
```
##📊 Verify Kubernetes Resources
###Check Pods
```sh
kubectl get pods
```
###Check Services
```sh
kubectl get svc
```
###Check Ingress
```sh
kubectl get ingress
```
###Check HPA
```sh
kubectl get hpa
```
##🌐 Accessing the Application
▶ If using Minikube:
Get Minikube IP

minikube ip
Open the app in browser:

http://<minikube-ip>
▶ If using GKE/AKS/Cloud K8s:
Get external IP

kubectl get svc
Visit in browser:

http://<external-ip>
##⚡ Autoscaling Demo
To simulate CPU load and test the autoscaler:

Start a load generator:
kubectl run -it load-generator --image=busybox /bin/sh
Inside the container:
while true; do wget -q -O- http://devops-service; done
Verify autoscaling:
kubectl get hpa
kubectl get pods
