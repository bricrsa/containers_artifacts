kubectl get pods

kubectl apply -f aks_deployment/trips.yml

kubectl get pods

kubectl exec oh-team5-trips-7857fcb9b6-65b8p -it sh


curl -i -X GET 'http://localhost:80/api/trips' 