# app-crud-kubernetes

helm install app-crud-postgresql bitnami/postgresql -f values.yaml

kubectl apply -f config.yaml -f job-migrations.yaml

kubectl apply -f deployment.yaml -f service.yaml -f ingress.yaml

kubectl delete daemonsets,replicasets,services,deployments,pods,rc,ingress,job --all --all-namespaces
