# springboot-crud-k8s
Run &amp; Deploy Spring Boot CRUD Application With MySQL on K8S

**Building image of the Application.**
minikube docker-env
Goto your project directory 
docker build -t springboot-crud-k8s:1.0 .
docker images

**steps - without use of secret and configmap**
kubectl apply -f db-deployment_1.yaml
kubectl apply -f app-deployment_1.yaml

**steps - with use of secret and configmap**
kubectl apply -f mysql-configMap.yaml
kubectl get cm db-config
kubectl describe cm db-config

kubectl apply -f mysql-secrets.yaml
kubectl get secrets mysql-secrets
kubectl describe secrets mysql-secrets

kubectl apply -f db-deployment.yaml
kubectl apply -f app-deployment.yaml