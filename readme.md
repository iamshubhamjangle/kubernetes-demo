# Kubernetes Demo

### Structure

UI -> MongoExpress -> MongoDB

```
MongoDB
    - Deployment file (mongodb-deployment.yaml)
    - Container Port (27017)
    - MONGO_INITDB_ROOT_USERNAME (secret.yaml)
    - MONGO_INITDB_ROOT_PASSWORD (secret.yaml)

MongoExpress
    - Deployment file (express-deployment.yaml)
    - Container Port (8081)
    - ME_CONFIG_MONGODB_ADMINUSERNAME (secret.yaml)
    - ME_CONFIG_MONGODB_ADMINPASSWORD (secret.yaml)
    - ME_CONFIG_MONGODB_SERVER (configmap.yaml)
    - External Port (30000)
```

- Username: admin
- Password: pass

### Commands

```js
kubectl get deployment
kubectl get pod
kubectl get pods -o wide    // Get pods with IP addresses
kubectl get service
kubectl get secret
kubectl get configmap
kubectl get replicaset
kubectl delete deployment <deployment_name>
```

```js
kubectl apply -f express-deployment.yaml
kubectl delete -f express-deployment.yaml
```

```js
kubectl logs <pod_name>
kubectl describe service <service_name>
```

```js
// In minikube environment external IP address is not assigned automatically, hence this step is needed to tunnel the IP adress
minikube service mongo-express-service
```
