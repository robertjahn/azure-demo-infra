# Overview

Contains subfolders with scripts to create and remove Azure resources
using Azure Resources Manager (ARM) templates.  

Assumes you have:
* Azure Cloud account 
* Dynatrace account
* Azure CLI tools installed
* Run scripts from unix terminal

## dtcli-webproxy-container

Makes a VM with with the Dynatrace One Agent Extention.

## vm-oneagent

Makes a container instance running a docker image

# Setup

* Lookup your Azure subscription ID
* Lookup your Dyantrace tenantId and token for the One Agent setup
* clone this repo
* within the each subfolder, make a a file called ```subscription.txt``` with the value of you Azure subscription id. The ```.gitignore``` will prevent this from being checked in
* within the Makefile you can optionally adjust region in the variables section
* Make a copy of ```parameters_template.json``` to ```parameters.json``` and update with YOUR_DT_VALUES

# Run

Within a subfolder, run ```make``` to see help for the make command options

Scripts that require Dynatrace account information, will prompt for this. For example
```
Please provide string value for 'tenantId' (? for help): 
Please provide string value for 'token' (? for help): 
```
NOTE: you can run it directly, but the Makefile will run the ```deploy.sh``` script. This script provided within Microsoft the web UI.
