#Install azure cli -- https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli
az --version # to check cli version
#Install azure aks cli
az aks install-cli # run from command prompt or powershell
#Then onpen visual studio code and run the commands from powershell terminal

#Azure CLI command
az login --tenant "6c497b5d-9c1b-4c0b-bb4a-58ec11153372"

## Create one aks cluster using azure portal
az aks get-credentials --resource-group kubernetes-poc --name aks-poc-ne001
kubectl get nodes -o wide 

# List Namespaces
kubectl get namespaces
kubectl get ns

# List Pods from all namespaces
kubectl get pods --all-namespaces

# List all k8s objects from Cluster Control plane
kubectl get all --all-namespaces

	#Create a folder kube-manifest
	#Create 2 files – deployment.yml and loadbalancer.yml


# Deploy Application
kubectl apply -f kube-manifests/

# Verify Pods
kubectl get pods

# Verify Deployment
kubectl get deployment

# Verify Service (Make a note of external ip)
kubectl get service

# Access Application
http://<External-IP-from-get-service-output>

# Delete Applications
kubectl delete -f kube-manifests/
