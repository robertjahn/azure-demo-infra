# Overview

Contains subfolders with scripts to create and remove Azure resources
using Azure Resources Manager (ARM) templates.  

Assumes you have:
* Azure Cloud account 
* Dynatrace account
* Azure CLI tools installed
* Run scripts from unix terminal

# Setup

* Lookup your Azure subscription ID
* Lookup your Dyantrace tenantId and token for the One Agent setup.
* clone this repo
* Make a copy of ```variables_template.csv``` to ```variables.csv` and update with your desired values
* Make a copy of ```parameters_template.json``` to ```parameters.json` and update with YOUR_DT_VALUES

# Run

Within a subfolder, run the ```./xxx_deploy.sh``` or ```./xxx_remove.sh``` scripts as required.

Do not run the ```deploy.sh``` script directly. It is a generic script provided by Microsoft the web UI.
