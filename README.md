# Assignment -3

This repository contains solutions to various Azure infrastructure tasks. Each task involves creating and managing different Azure resources. Below is a detailed description of each assignment along with relevant screenshots.

## 1. Compute Resources

### Task:
Provision and manage compute resources on Azure.

### Steps:
1. Navigate to the Azure portal.
2. Create a new Virtual Network.
   ```sh
   az network vnet create --name MyVNet --resource-group MyResourceGroup --subnet-name MySubnet
Configure the necessary subnets.

az network vnet subnet create --address-prefix 10.0.1.0/24 --name MySubnet --resource-group MyResourceGroup --vnet-name MyVNet

Deploy virtual machines within the virtual network
az vm create --resource-group MyResourceGroup --name MyVM --image UbuntuLTS --vnet-name MyVNet --subnet MySubnet --admin-username azureuser --generate-ssh-keys

### Steps:

Create a Linux virtual machine.

az vm create --resource-group MyResourceGroup --name MyLinuxVM --image UbuntuLTS --admin-username azureuser --generate-ssh-keys


Create a Windows virtual machine.

az vm create --resource-group MyResourceGroup --name MyWindowsVM --image Win2019Datacenter --admin-username azureuser --admin-password myPassword123!
Access the Linux VM using SSH.

ssh azureuser@<Linux_VM_IP_Address>

Access the Windows VM using RDP.

Open Remote Desktop Connection.
Enter the IP address of the Windows VM.
Connect using your credentials.


### 3. Create an App Service Plan
Task:
Create an App Service Plan, provision a web app in the existing plan, and deploy a simple welcome page.

# Steps:
### Create a new App Service Plan.

az appservice plan create --name MyAppServicePlan --resource-group MyResourceGroup --sku FREE
Provision a Web App within the App Service Plan.

az webapp create --resource-group MyResourceGroup --plan MyAppServicePlan --name MyUniqueAppName
Deploy a simple HTML welcome page to the Web App.

az webapp up --name MyUniqueAppName --resource-group MyResourceGroup --html


### 4. Create Azure Container Registry (ACR) and Pull Image
Task:
Create an Azure Container Registry (ACR), pull an image from ACR, and create a container from it.

Steps:
Create a new Azure Container Registry (ACR).

az acr create --resource-group MyResourceGroup --name MyACR --sku Basic
Push a Docker image to the ACR.

az acr login --name MyACR
docker tag myapp:latest MyACR.azurecr.io/myapp:latest
docker push MyACR.azurecr.io/myapp:latest
Pull the Docker image from the ACR.

docker pull MyACR.azurecr.io/myapp:latest
Create a container from the pulled image.

az container create --resource-group MyResourceGroup --name mycontainer --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5 --registry-login-server MyACR.azurecr.io --registry-username <username> --registry-password <password>


### 5. Create Container Instance
Task:
Create a container instance, deploy a simple Docker application, create container groups, and test functionality.

# Steps:
Create a new container instance in Azure.

az container create --resource-group MyResourceGroup --name mycontainer --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5
Deploy a Docker application to the container instance.

az container create --resource-group MyResourceGroup --name mydockerapp --image mydockerapp:latest --cpu 1 --memory 1.5
Create container groups for better organization and scaling.

az container create --resource-group MyResourceGroup --name mycontainergroup --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5 --restart-policy Always

Test the functionality of the deployed application.

az container show --resource-group MyResourceGroup --name mycontainer --query instanceView.state


Additional Information
For detailed steps and code snippets used in each assignment, please refer to the respective commands provided above.

### Screenshots 
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20202631.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20225333.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20235151.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20000850.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20002601.png
