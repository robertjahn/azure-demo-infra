default: help

# Adjust to your needs
resourceGroupLocation = eastus
# edit subscription.txt file with your value
$(eval subscriptionId=`cat subscription.txt`)
# dont edit these unless you adjust the ARM templates too
resourceGroupName = DemoVM
deploymentName = DemoVMDeploy
vmName = DemoVM

help:
	@echo Current values to be used in scripts.  Fix if not correct
	@echo " subscriptionId="$(subscriptionId)
	@echo " resourceGroupLocation"=$(resourceGroupLocation)
	@echo " resourceGroupName"=$(resourceGroupName)
	@echo " deploymentName"=$(deploymentName)
	@echo " vmName"=$(vmName)

vm_deploy:
	@echo Deploying ...
	./deploy.sh -i $(subscriptionId) -g $(resourceGroupName) -n $(deploymentName) -l $(resourceGroupLocation)
	@echo Getting current VMs...
	az vm list -o table
	@echo Done

vm_remove:
	@echo Getting current VMs...
	az vm list -o table
	@echo About to remove $vmName
	az vm delete -n $(vmName) -g $(resourceGroupName)
	@echo Getting current VMs...
	az container list -o table
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