# helper file

az login

az aks get-credentials --resource-group teamResources --name ohteam5cluster --admin

kubectl get pods

kubectl logs oh-team5-poi-795dd96994-bdl4z

kubectl create deployment oh-team5-trips --image registryrbq9427.azurecr.io/tripinsights/trips:1.0 --dry-run -o yaml

kubectl apply -f trips.yml

kubectl get pods

kubectl describe deployment oh-team5-poi

kubectl create deployment oh-team5-java --image registryrbq9427.azurecr.io/tripinsights/user-java:1.0 --dry-run -o yaml

tripinsights/user-java

kubectl expose deployment oh-team5-trips --type=NodePort --name=trips-svc --dry-run=client -o yaml --port 8000

kubectl create secret generic sqlsecrets --from-literal=username=<username> --from-literal=password=<password> --from-literal=server=<dbname> -n api

az aks enable-addons --addons azure-keyvault-secrets-provider --name myAKSCluster --resource-group TeamResources

kubectl get pods -n kube-system -l 'app in (secrets-store-csi-driver, secrets-store-provider-azure)'

step1
az aks enable-addons --addons http_application_routing --name myAKSCluster --resource-group teamResources

step2
az aks show --resource-group teamResources --name myAKSCluster --query addonProfiles.httpApplicationRouting.config.HTTPApplicationRoutingZoneName -o table

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

NAMESPACE=ingress-basic

helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx --create-namespace --namespace ingress

kubectl --namespace ingress get services -o wide -w ingress-nginx-controller
