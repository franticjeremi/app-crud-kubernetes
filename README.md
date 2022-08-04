# app-crud-kubernetes

kubectl create namespace m && helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx/ && helm repo update && helm install nginx ingress-nginx/ingress-nginx --namespace m -f nginx-ingress.yaml

kubectl create namespace postgres
helm -n postgres install app-crud-postgresql bitnami/postgresql -f values.yaml

kubectl apply -f config.yaml -f job-migrations.yaml

kubectl apply -f config.yaml -f deployment.yaml -f service.yaml -f ingress.yaml

newman run user.postman_collection.json

kubectl delete daemonsets,replicasets,services,deployments,pods,rc,ingress,job --all --all-namespaces