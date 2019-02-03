default: help

# edit subscription.txt file with your value
$(eval subscriptionId=`cat subscription.txt`)
# dont edit these unless you adjust the ARM templates too
resourceGroupName = rjahn-demo-group-aks
deploymentName = demo-aks-deployment
resourceGroupLocation = eastus
aksName = rjahn-demo-acm-cluster

help:
	@echo Current values to be used in scripts.  Fix if not correct
	@echo " subscriptionId="$(subscriptionId)
	@echo " resourceGroupLocation"=$(resourceGroupLocation)
	@echo " resourceGroupName"=$(resourceGroupName)
	@echo " deploymentName"=$(deploymentName)
	@echo " aksName"=$(aksName)

aks_deploy:
	@echo Deploying ...
	./deploy.sh -i $(subscriptionId) -g $(resourceGroupName) -n $(deploymentName) -l $(resourceGroupLocation)
	@echo Getting current Kubernetes Clusters...
	az aks list -o table
	@echo Done

aks_remove:
	@echo Getting current Kubernetes Clusters...
	az aks list -o table
	@echo About to remove $aksName
	az aks delete -n $(aksName) -g $(resourceGroupName)
	@echo Getting current Kubernetes Clusters...
	az aks list -o table
	@echo Done

group_deploy:
	@echo Getting current Resource Groups...
	 az group list -o table
	@echo About to deploy $(resourceGroupName)
	az group create -g $(resourceGroupName) -l $(resourceGroupLocation)
	@echo Getting current Resource Groups...
	 az group list -o table
	@echo Done

group_remove:
	@echo Getting current Resource Groups...
	 az group list -o table
	@echo About to remove $(resourceGroupName)
	az group delete -g $(resourceGroupName)
	@echo Getting current Resource Groups...
	 az group list -o table
	@echo Done
