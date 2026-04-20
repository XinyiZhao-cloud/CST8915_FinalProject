# Best Buy Cloud-Native App - Service Plan

## Microservices
1. store-front
Customer-facing web application for browsing products and placing orders.

2. store-admin
Admin web application for employees to add, update, and manage products, and monitor orders.

3. product-service
REST API for product CRUD operations.

4. order-service
REST API for order creation and retrieval.

5. makeline-service
Background worker that updates order statuses from Pending to Processing to Completed.

## Database
MongoDB will store product and order data.

## Deployment Target
All services will be containerized and deployed to Azure Kubernetes Service (AKS).

# Best Buy Cloud-Native Application

## Architecture
(Insert diagram)

## Services
- Store-Front
- Product-Service
- Order-Service
- Makeline-Service

## Deployment Instructions

### 1. Apply Kubernetes files
kubectl apply -f deployment-files/product-service.yaml
kubectl apply -f deployment-files/order-service.yaml
kubectl apply -f deployment-files/store-front.yaml

### 2. Get external IP
kubectl get services

## Docker Images
| Service | Image |
|--------|------|
| Product | xyzhao0201/bestbuy-product-service:v1 |
| Order | xyzhao0201/bestbuy-order-service:v1 |
| Store Front | xyzhao0201/bestbuy-store-front:v1 |