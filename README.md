#  Docker & Kubernetes Daily Activity Commands Cheat Sheet

---

#  Docker Commands

# 1. Docker Information Commands

## Check Docker Version
```bash
docker --version
```

## Detailed Docker Info
```bash
docker info
```

## Check Docker System Usage
```bash
docker system df
```

---

# 2. Docker Image Commands

## List Docker Images
```bash
docker images
```

## Pull Docker Image
```bash
docker pull nginx
```

## Build Docker Image
```bash
docker build -t myapp .
```

## Build Image with Version
```bash
docker build -t myapp:v1 .
```

## Remove Docker Image
```bash
docker rmi <image-id>
```

## Remove Dangling Images
```bash
docker image prune
```

---

# 3. Docker Container Commands

## Run Container
```bash
docker run nginx
```

## Run Container in Detached Mode
```bash
docker run -d nginx
```

## Run Container with Port Mapping
```bash
docker run -d -p 3000:3000 myapp
```

## Run Container with Name
```bash
docker run -d --name mycontainer nginx
```

## List Running Containers
```bash
docker ps
```

## List All Containers
```bash
docker ps -a
```

## Stop Container
```bash
docker stop <container-id>
```

## Start Container
```bash
docker start <container-id>
```

## Restart Container
```bash
docker restart <container-id>
```

## Remove Container
```bash
docker rm <container-id>
```

## Remove All Stopped Containers
```bash
docker container prune
```

---

# 4. Docker Logs & Debugging Commands

## View Container Logs
```bash
docker logs <container-id>
```

## Live Logs
```bash
docker logs -f <container-id>
```

## Execute Inside Container
```bash
docker exec -it <container-id> sh
```

OR

```bash
docker exec -it <container-id> bash
```

## Inspect Container
```bash
docker inspect <container-id>
```

## Container Resource Usage
```bash
docker stats
```

---

# 5. Docker Volume Commands

## List Volumes
```bash
docker volume ls
```

## Create Volume
```bash
docker volume create myvolume
```

## Inspect Volume
```bash
docker volume inspect myvolume
```

## Remove Volume
```bash
docker volume rm myvolume
```

---

# 6. Docker Network Commands

## List Networks
```bash
docker network ls
```

## Create Network
```bash
docker network create mynetwork
```

## Inspect Network
```bash
docker network inspect mynetwork
```

## Connect Container to Network
```bash
docker network connect mynetwork container-name
```

---

# 7. Docker Compose Commands

## Start Docker Compose
```bash
docker compose up
```

## Run Compose in Background
```bash
docker compose up -d
```

## Stop Compose
```bash
docker compose down
```

## Rebuild Compose
```bash
docker compose up --build
```

## Compose Logs
```bash
docker compose logs
```

## Compose Running Containers
```bash
docker compose ps
```

---

# ☸️ Kubernetes Commands

# 1. Cluster Commands

## Cluster Information
```bash
kubectl cluster-info
```

## Kubernetes Version
```bash
kubectl version
```

## Check Nodes
```bash
kubectl get nodes
```

## Detailed Nodes Information
```bash
kubectl get nodes -o wide
```

## Describe Node
```bash
kubectl describe node <node-name>
```

---

# 2. Namespace Commands

## List Namespaces
```bash
kubectl get ns
```

## Create Namespace
```bash
kubectl create namespace dev
```

## Delete Namespace
```bash
kubectl delete namespace dev
```

---

# 3. Pod Commands

## Create Nginx Pod
```bash
kubectl run nginx --image=nginx
```
## List Pods
```bash
kubectl get pods
```

## List Pods in All Namespaces
```bash
kubectl get pods -A
```

## Detailed Pod Output
```bash
kubectl get pods -o wide
```

## Describe Pod
```bash
kubectl describe pod <pod-name>
```

## Pod Logs
```bash
kubectl logs <pod-name>
```

## Live Pod Logs
```bash
kubectl logs -f <pod-name>
```

## Execute Inside Pod
```bash
kubectl exec -it <pod-name> -- sh
```

## Delete Pod
```bash
kubectl delete pod <pod-name>
```

---

# 4. Deployment Commands

## Create Deployment
```bash
kubectl create deployment nginx --image=nginx
```

## List Deployments
```bash
kubectl get deployments
```

## Describe Deployment
```bash
kubectl describe deployment nginx
```

## Scale Deployment
```bash
kubectl scale deployment nginx --replicas=3
```

## Restart Deployment
```bash
kubectl rollout restart deployment nginx
```

## Deployment History
```bash
kubectl rollout history deployment nginx
```

## Rollback Deployment
```bash
kubectl rollout undo deployment nginx
```

## Delete Deployment
```bash
kubectl delete deployment nginx
```

---

# 5. Service Commands

## List Services
```bash
kubectl get svc
```

## Expose Deployment
```bash
kubectl expose deployment nginx --port=80 --type=NodePort
```

## Describe Service
```bash
kubectl describe svc nginx
```

## Delete Service
```bash
kubectl delete svc nginx
```

---

# 6. YAML Commands

## Apply YAML File
```bash
kubectl apply -f deployment.yaml
```

## Delete YAML Resources
```bash
kubectl delete -f deployment.yaml
```

## Validate YAML
```bash
kubectl apply --dry-run=client -f deployment.yaml
```

---

# 7. ConfigMap Commands

## Create ConfigMap
```bash
kubectl create configmap app-config --from-literal=env=prod
```

## Get ConfigMaps
```bash
kubectl get configmaps
```

## Describe ConfigMap
```bash
kubectl describe configmap app-config
```

---

# 8. Secret Commands

## Create Secret
```bash
kubectl create secret generic db-secret --from-literal=password=123456
```

## Get Secrets
```bash
kubectl get secrets
```

## Describe Secret
```bash
kubectl describe secret db-secret
```

---

# 9. Monitoring Commands

## Node Resource Usage
```bash
kubectl top node
```

## Pod Resource Usage
```bash
kubectl top pod
```

---

# 10. Troubleshooting Commands

## Get Events
```bash
kubectl get events
```

## Explain Kubernetes Resource
```bash
kubectl explain deployment
```

## Get All Resources
```bash
kubectl get all
```

## Watch Pods Live
```bash
kubectl get pods -w
```

---

#  Most Frequently Asked Interview Commands

# Docker Interview Commands

## Build Docker Image
```bash
docker build -t app .
```

## Run Docker Container
```bash
docker run -d -p 3000:3000 app
```

## View Logs
```bash
docker logs -f <container-id>
```

## Execute Inside Container
```bash
docker exec -it <container-id> sh
```

## Remove All Stopped Containers
```bash
docker container prune
```

---

# Kubernetes Interview Commands

## Get Pods
```bash
kubectl get pods
```

## Describe Pod
```bash
kubectl describe pod <pod-name>
```

## Pod Logs
```bash
kubectl logs <pod-name>
```

## Create Deployment
```bash
kubectl create deployment nginx --image=nginx
```

## Scale Deployment
```bash
kubectl scale deployment nginx --replicas=3
```

## Restart Deployment
```bash
kubectl rollout restart deployment nginx
```

## Apply YAML
```bash
kubectl apply -f deployment.yaml
```

## Expose Deployment
```bash
kubectl expose deployment nginx --port=80 --type=NodePort
```

## Get Services
```bash
kubectl get svc
```

## Get Nodes
```bash
kubectl get nodes -o wide
```

---

#  Most Common Kubernetes Errors

| Error | Reason |
|---|---|
| Pending | Insufficient CPU/RAM |
| CrashLoopBackOff | Application crash |
| ImagePullBackOff | Docker image issue |
| ErrImagePull | Wrong image name |
| OOMKilled | Memory exceeded |
| NodeNotReady | Node issue |
| FailedScheduling | No resources available |

---

# 🔥 Real Production Troubleshooting Flow

```bash
kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl get svc
kubectl get endpoints
kubectl describe nodes
```

---

# 🚀 Production Architecture Flow

```text
Developer
   ↓
Docker Build
   ↓
Docker Push
   ↓
Kubernetes Deployment
   ↓
Pods
   ↓
Service
   ↓
Ingress
   ↓
Users
```

---

#  Important DevOps Concepts

| Tool | Purpose |
|---|---|
| Docker | Containerization |
| Kubernetes | Container Orchestration |
| Helm | Kubernetes Package Manager |
| Jenkins | CI/CD |
| ArgoCD | GitOps |
| Terraform | Infrastructure as Code |
| Prometheus | Monitoring |
| Grafana | Visualization |

---

#  Most Important Commands to Remember

```bash
docker ps
docker images
docker logs -f <container-id>
docker exec -it <container-id> sh

kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl get svc
kubectl apply -f deployment.yaml
kubectl rollout restart deployment nginx
```
