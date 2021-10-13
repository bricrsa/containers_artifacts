# helper file

az login

az aks get-credentials --resource-group teamResources --name ohteam5cluster --admin

kubectl get pods

kubectl logs oh-team5-poi-795dd96994-bdl4z

kubectl create deployment oh-team5-trips --image registryrbq9427.azurecr.io/tripinsights/trips:1.0 --dry-run -o yaml

kubectl apply -f trips.yml

kubectl get pods

kubectl describe deployment oh-team5-poi


kubectl create deployment userprofile --image registryrbq9427.azurecr.io/tripinsights/userprofile:1.0 --dry-run=client -o yaml

kubectl create secret generic sqlpassword \
    --namespace default \
    --from-literal=SQL_PASSWORD="mypasswordmonkey123"

kubectl create secret generic sqlsecrets --from-literal=username=<username> --from-literal=password=<password> --from-literal=server=<servername>