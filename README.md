# Assignment -3

This repository contains solutions to various Azure infrastructure tasks. Each task involves creating and managing different Azure resources. Below is a detailed description of each assignment along with relevant screenshots.

## 1. Compute Resources

### Task:
Provision and manage compute resources on Azure.

### Steps:
1. Navigate to the Azure portal.
2. Create a new Virtual Network.
3. Configure the necessary subnets.
4. Deploy virtual machines within the virtual network.

### Resources:
- [Virtual Networks Overview](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview)

### Screenshot:
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20202631.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20225333.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-06%20235151.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20000850.jpg
https://github.com/jayant77778/Assignment-3-/blob/main/Screenshot%202024-06-07%20002601.png


## 2. Deploy Linux and Windows Virtual Machines
3. Create an App Service Plan
Task:
Create an App Service Plan, provision a web app in the existing plan, and deploy a simple welcome page.

Steps:
Create a new App Service Plan.
Provision a Web App within the App Service Plan.
Deploy a simple HTML welcome page to the Web App.
Resources:
Virtual Networks Overview
Screenshot:

4. Create Azure Container Registry (ACR) and Pull Image
Task:
Create an Azure Container Registry (ACR), pull an image from ACR, and create a container from it.

Steps:
Create a new Azure Container Registry (ACR).
Push a Docker image to the ACR.
Pull the Docker image from the ACR.
sh
Copy code
docker pull <ACR_Username>.azurecr.io/<Image_Name>:<Tag>
Create a container from the pulled image.
Resources:
Virtual Networks Overview
Screenshot:

5. Create Container Instance
Task:
Create a container instance, deploy a simple Docker application, create container groups, and test functionality.

Steps:
Create a new container instance in Azure.
Deploy a Docker application to the container instance.
Create container groups for better organization and scaling.
Test the functionality of the deployed application.
Resources:
Virtual Networks Overview
Screenshot:

Additional Information
For detailed steps and code snippets used in each assignment, please refer to the respective resource links provided above.


### Task:
Deploy both Linux and Windows virtual machines and access them using SSH and RDP.

### Steps:
1. Create a Linux virtual machine.
2. Create a Windows virtual machine.
3. Access the Linux VM using SSH.
   ```sh
   ssh azureuser@<Linux_VM_IP_Address>
   Access the Windows VM using RDP.
Open Remote Desktop Connection.
Enter the IP address of the Windows VM.
Connect using your credentials.
