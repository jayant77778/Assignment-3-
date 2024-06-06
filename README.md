```markdown
# Azure Infrastructure Tasks - Assignment 3

This repository provides solutions to various Azure infrastructure tasks. Each task involves creating and managing different Azure resources. Below is a detailed description of each assignment, including commands and relevant screenshots.

## 1. Compute Resources

### Task:
Provision and manage compute resources on Azure.

#### Create a Virtual Network
```sh
az network vnet create --name MyVNet --resource-group MyResourceGroup --subnet-name MySubnet
az network vnet subnet create --address-prefix 10.0.1.0/24 --name MySubnet --resource-group MyResourceGroup --vnet-name MyVNet
```

#### Deploy Virtual Machines within the Virtual Network

**Create a Linux VM**
```sh
az vm create --resource-group MyResourceGroup --name MyLinuxVM --image UbuntuLTS --admin-username azureuser --generate-ssh-keys
```

**Create a Windows VM**
```sh
az vm create --resource-group MyResourceGroup --name MyWindowsVM --image Win2019Datacenter --admin-username azureuser --admin-password myPassword123!
```

#### Access the Virtual Machines

**Access the Linux VM using SSH**
```sh
ssh azureuser@<Linux_VM_IP_Address>
```

**Access the Windows VM using RDP**
1. Open Remote Desktop Connection.
2. Enter the IP address of the Windows VM.
3. Connect using your credentials.

## 2. Create an App Service Plan

### Task:
Create an App Service Plan, provision a web app in the existing plan, and deploy a simple welcome page.

## 3. Create a new App Service Plan
```sh
az appservice plan create --name MyAppServicePlan --resource-group MyResourceGroup --sku FREE
```

#### Provision a Web App within the App Service Plan
```sh
az webapp create --resource-group MyResourceGroup --plan MyAppServicePlan --name MyUniqueAppName
```

#### Deploy a Simple HTML Welcome Page to the Web App
```sh
az webapp up --name MyUniqueAppName --resource-group MyResourceGroup --html
```

## 4. Create Azure Container Registry (ACR) and Pull Image

### Task:
Create an Azure Container Registry (ACR), push a Docker image to ACR, and create a container from it.

#### Create a New Azure Container Registry (ACR)
```sh
az acr create --resource-group MyResourceGroup --name MyACR --sku Basic
```

#### Push a Docker Image to the ACR
```sh
az acr login --name MyACR
docker tag myapp:latest MyACR.azurecr.io/myapp:latest
docker push MyACR.azurecr.io/myapp:latest
```

#### Pull the Docker Image from the ACR
```sh
docker pull MyACR.azurecr.io/myapp:latest
```

#### Create a Container from the Pulled Image
```sh
az container create --resource-group MyResourceGroup --name mycontainer --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5 --registry-login-server MyACR.azurecr.io --registry-username <username> --registry-password <password>
```

## 4. Create Container Instance

### Task:
Create a container instance, deploy a simple Docker application, create container groups, and test functionality.

#### Create a New Container Instance in Azure
```sh
az container create --resource-group MyResourceGroup --name mycontainer --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5
```

#### 5. Deploy a Docker Application to the Container Instance
```sh
az container create --resource-group MyResourceGroup --name mydockerapp --image mydockerapp:latest --cpu 1 --memory 1.5
```

#### Create Container Groups for Better Organization and Scaling
```sh
az container create --resource-group MyResourceGroup --name mycontainergroup --image MyACR.azurecr.io/myapp:latest --cpu 1 --memory 1.5 --restart-policy Always
```

#### Test the Functionality of the Deployed Application
```sh
az container show --resource-group MyResourceGroup --name mycontainer --query instanceView.state
```

## Screenshots(answers)

![Screenshot 1](https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20202631.jpg)
![Screenshot 2](https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20225333.jpg)
![Screenshot 3](https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20235151.jpg)
![Screenshot 4](https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20000850.jpg)
![Screenshot 5](https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20002601.png)
```
