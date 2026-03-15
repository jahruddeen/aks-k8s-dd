# 🚀 AKS Kubernetes Deployment with Azure DevOps CI/CD

This project demonstrates a complete **DevOps pipeline** for deploying a Node.js application to **Azure Kubernetes Service (AKS)** using **Docker, Azure Container Registry (ACR), and Azure DevOps**.

---

# 📌 Project Architecture

Developer → GitHub → Azure DevOps Pipeline → Docker Build → Azure Container Registry → AKS Cluster → LoadBalancer Service → Application Access

---

# 🛠 Technologies Used

- Docker
- Kubernetes
- Azure Kubernetes Service (AKS)
- Azure Container Registry (ACR)
- Azure DevOps
- GitHub
- Linux (Ubuntu VM)

---

# 📂 Project Structure

aks-k8s-dd
│
├── Dockerfile
├── README.md
├── app
│ └── Node.js Application
│
└── kubernetes
├── deployment.yml
├── service.yml
├── aks-sc.yml
├── aks-pv.yml
└── aks-pvc.yml
-----------------------------------------


---

# ⚙️ Setup Instructions

## 1️⃣ Clone Repository


git clone https://github.com/jahruddeen/aks-k8s-dd.git

cd aks-k8s-dd



------------------------------------------------------------------
---

# 🐳 Build Docker Image


docker build -t node-devops-app .


---------------------------------------------------------------------------
---

# 📦 Push Image to Azure Container Registry


docker tag node-devops-app <ACR_NAME>.azurecr.io/node-devops-app:v1
docker push <ACR_NAME>.azurecr.io/node-devops-app:v1


---

# ☸️ Deploy to AKS

Apply Kubernetes manifests:


kubectl apply -f aks-sc.yml
kubectl apply -f aks-pv.yml
kubectl apply -f aks-pvc.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml


---

# 🔎 Check Deployment


kubectl get pods
kubectl get svc
kubectl get pv
kubectl get pvc


---

# 🌐 Access Application


kubectl get svc


Use the **EXTERNAL-IP** of the LoadBalancer service.

---

# 🔄 CI/CD Pipeline (Azure DevOps)

Pipeline performs:

1️⃣ Pull code from GitHub  
2️⃣ Build Docker image  
3️⃣ Push image to Azure Container Registry  
4️⃣ Deploy to AKS cluster automatically  

---

# 📊 Kubernetes Resources Used

| Resource | Purpose |
|--------|--------|
| Deployment | Manages application pods |
| Service | Exposes application |
| StorageClass | Dynamic storage provisioning |
| PersistentVolume | Storage for application |
| PersistentVolumeClaim | Request storage |

---

# 👨‍💻 Author

**Jahruddeen Ansari**

DevOps Engineer | Azure | Kubernetes | Docker | CI/CD

GitHub: https://github.com/jahruddeen

---

# ⭐ If you like this project

Give the repository a **star ⭐**
🚀 After Adding README

Run:

git add README.md
git commit -m "Added professional README"
git push origin main
