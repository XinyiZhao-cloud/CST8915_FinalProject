# CST8915: FCloud-Native App for Best Buy

**Student Name**: Xinyi Zhao    
**Student ID**: 040953633    
**Course**: CST8915 Full-stack Cloud-native Development
Applications   
**Semester**: Winter 2026   

# 🛒 Cloud-Native Microservices Application (Best Buy Demo)

## 📌 Overview
This project is a cloud-native microservices application developed as part of a Full-Stack Cloud-Native Developer role simulation.

The system is designed based on a microservices architecture similar to the **Algonquin Pet Store (On Steroids)** model. It demonstrates containerization, Kubernetes deployment, and CI/CD automation using GitHub Actions.

---

## 🏗️ Architecture

> 📎 Architecture Diagram:  
(Add your Draw.io / image link here)

The application consists of **5 microservices and 1 database**:

- **Store-Front** – Customer-facing web application  
- **Store-Admin** – Employee/admin web application  
- **Order-Service** – Handles order processing  
- **Product-Service** – Manages product catalog  
- **Makeline-Service** – Background worker for order processing  
- **MongoDB** – Stateful database  

---

## ⚙️ Design Choices

- **Microservices Architecture**: Improves scalability and modularity  
- **Docker Containers**: Ensures consistent environments across development and deployment  
- **Azure Kubernetes Service (AKS)**: Manages container orchestration  
- **MongoDB**: Flexible NoSQL database for product and order data  
- **GitHub Actions CI/CD**: Automates build and deployment pipelines  

---

## 🚀 Deployment (Kubernetes)

All services are deployed to **Azure Kubernetes Service (AKS)**.

### Key Configuration:
- **ConfigMaps** → Store environment variables  
- **Secrets** → Store sensitive data (connection strings, credentials)  
- **StatefulSet** → Used for MongoDB (stateful workload)  
- **Services** → Expose microservices internally/externally  

### Deployment Steps:
1. Build Docker images for each service  
2. Push images to Docker Hub  
3. Apply Kubernetes manifests:
   ```bash
   kubectl apply -f Deployment-Files/
4. Verify pods and services:
```bash
kubectl get pods
kubectl get services
```

## 🔄 CI/CD Pipeline

Each microservice has its own GitHub Actions pipeline that:
* Builds Docker image
* Pushes to Docker Hub
* Deploys to Kubernetes (AKS)

Pipelines are triggered on:
* Code push
* Pull request (optional)

## 🌐 Demo Shop Endpoints

> ⚠️ **Note:** The following demo endpoints were used during testing and presentation.  
> Azure resources have been **decommissioned to reduce costs**, so these services are currently unavailable.

| Service       | Endpoint             | Status     |
|--------------|----------------------|------------|
| Store Front  | http://20.14.61.92   | ❌ Offline |
| Admin Panel  | http://4.242.209.167 | ❌ Offline |

## 🔗 Microservices Repositories

### 🛍️ Store Front Service

Frontend application for user interaction and product browsing.
👉 https://github.com/XinyiZhao-cloud/final-store-front


### 📦 Product Service

Handles product catalog, inventory, and product-related APIs.
👉 https://github.com/XinyiZhao-cloud/final-product-service


### 🧾 Order Service

Manages customer orders, order processing, and status tracking.
👉 https://github.com/XinyiZhao-cloud/final-order-service


### ⚙️ Makeline Service

Handles order workflow, processing logic, and background operations.
👉 https://github.com/XinyiZhao-cloud/final-makeline-service


### 🛠️ Admin Service

Provides administrative controls, monitoring, and management features.
👉 https://github.com/XinyiZhao-cloud/final-store-admin

## 📁 Deployment Files

All Kubernetes YAML manifests are located in:
 ```
Deployment-Files/
 ```
 Includes:
* Deployments
* Services
* ConfigMaps
* Secrets
* StatefulSet (MongoDB)

## 🎥 Video Demonstration

The video demo includes:
* Architecture overview
* Design decisions
* Store Front application demo (running and functionality)
* CI/CD pipeline in action (GitHub Actions)

> 📌 Video Demonstration

The video demonstration presents the overall architecture of the microservices application, explains the main design choices, and showcases the Store Front service in operation. It also includes an application walkthrough to demonstrate functionality, followed by the CI/CD pipeline in action using GitHub Actions for automated build and deployment.

[![Watch the Demo](https://img.youtube.com/vi/YOUR_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

---

### 🔗 Direct Link
👉 https://www.youtube.com/watch?v=YOUR_VIDEO_ID

## 💡 Notes

* Sensitive data is stored using environment variables and Kubernetes Secrets
* Resources were cleaned up after testing to control Azure costs
* The system can be redeployed using CI/CD pipelines

## 🤖 AI Assistance Disclosure

AI tools (ChatGPT) were used in this project to assist with formatting, documentation structure, and minor code guidance.  

All implementation, configuration, and final decisions were completed and verified independently.