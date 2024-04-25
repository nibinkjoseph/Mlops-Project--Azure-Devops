# Mlops-Project-Azure-Devops
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/d0f98999-8f31-4fd3-be7f-42638bc96fb4)


# Step 1: Log into dev.azure.com
         
         Create a project:
         Project Name: azure-devops-jan24

# Step 2: Go to Repos and import a repository
         Link: https://github.com/03sarath/Azure-CI-CD-static-app
         
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/15e1e47c-497f-437e-a101-adcd15ec4e21)

# Step 3: Go to portal.azure.com

## Go to App Services
         Create Static Web App
         Resource Group: azure-devops-jan24
         Static Web App Name: azure-devops-jan24
         Deployment details : Azure Devops
         Build Presents : Vue.js
         App location, Api Location no changes, and Output location: Dist

If the connection is not getting created then go back to devops portal and under project setting select Service connections under Pipelines
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/a2d23ed9-9697-4cf2-b250-b991fe069c38)

## Microsoft Entra ID
Select App Registrations : azure-devops-jan24
Copy all the Key details
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/9cc88c61-e441-4692-ae2d-28c4ca89bc29)

## Select Certificates & secrets
         + Client secret
         Description: azure-devops-jan24
         After adding copy the Value and Secret ID
## Go to Access Control (IAM)
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/5462a949-3f6f-44f4-875f-7f86afe2afb0)
+ Add Role Assignment
+ Select Privileged administrator roles
+ Contributer
+ Select member: azure-devops-jan24

Go back to azure devops page
Select project settings
+ Service connections
+ Azure Resource Manager
+ Service Principal Manual
+ Paste subscription id and name
+ Paste client id to service principal id
+ Paste value to service principal key
+ Paste tenant ID
+ Verify it
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/48a63530-4650-4ced-a768-7b8870193bf6)
Service connection name : devops-azure

## Go to App Services
         Create Static Web App
         Resource Group: azure-devops-jan24
         Static Web App Name: azure-devops-jan24
         Deployment details : Azure Devops
         Build Presents : Vue.js
         App location, Api Location no changes, and Output location: Dist
It still failed
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/b85f5e71-a3f6-44e2-a755-8698fd718a0e)








