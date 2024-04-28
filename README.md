# Mlops-Project-Azure-Devops
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/ad618cac-f7db-4bdb-817b-848f0b92b7c7)





# Step 1: Log into dev.azure.com
         
         Create a project:
         Project Name: devops-nibin-jan24

# Step 2: Go to Repos and import a repository
         Link: https://github.com/03sarath/Azure-CI-CD-static-app
         
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/15e1e47c-497f-437e-a101-adcd15ec4e21)

# Step 3: Go to portal.azure.com

## Go to App Services
         Create Static Web App
         Resource Group: azure-devops-jan24
         Static Web App Name: azure-devops-jan24
         Deployment details : Other
         Build Presents : Vue.js
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/3b59e7f4-e644-48e0-9dcc-bb28ca0031c3)

Click on to Manage Deployment Token
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/2d8d4dbe-90ac-4654-ab82-ed5e8c912c3c)

## Step 4: Go to the project in the dev.azure.com
         + Project settings
         + Under boards select Github connections
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/c069b128-1053-4aaa-af99-8f379a127da4)

Fork the repository if not done (Azure-CI-CD-static-app)
Now add the Github repositories
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/5f802795-3f55-4574-8fdf-65e9b904eb46)

Congrats!
The Github is connected!
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/2f271289-8b8f-4b70-baad-108e89988f9c)

## Step 5 : Create a folder ( I named as AZURE DEVOPS )
         Clone all the files from GitHub
         git clone https://github.com/nibinkjoseph/Azure-CI-CD-static-app.git


## Step 6: Go to pipeline in the devops portal
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/46e6bbf5-27ec-42e8-873b-f0edc714034f)

## Step 7: Before doing anything in the pipeline go to Boards as shown below
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/69aec12d-2961-42e1-9e4d-5a9cbfd8e67b)

         Create a task to change v12 to v10 in the readme file.
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/93ed968c-bc48-4fda-9ca0-fc26453881ff)

So we have made the change in the readme file.
Now open command prompt and commit it.
         git status
         
         git add .
         
         git commit -m "fixed AB#3"
         
         git push origin master

## Step 8: Go to Pipeline and create one.

         This is the YAML Pipeline Structure
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/0163b467-5c1c-43cc-aa1f-3fe0633d1d86)

This YAML file azure-static-app-build-deploySatage.yml
It will build and deploy the app to the staging environment



## Step 9: Go to Pipeline and connect to Github
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/6d0910a4-4c0a-478a-96d1-ab5758d8dbfb)

         Select Existing Azure Pipelines YAML file
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/b5aac5c6-2a4c-478c-8e93-456cbd42f7ea)

![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/06a12f0a-dc5d-4ae9-b71a-0a0f1edca972)

After clicking continue we will reach the page where we see variable at the right side. Select new variable
 
Name : deployment_token

Value: The value is the manage deployment token from the azure portal
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/a9022d1c-35a6-42fd-986b-4bc21190ba06)
![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/28c54dee-3cc1-435f-bd05-cc1462f04bea)


So now the Azure Devops portal have a configuration to access the Static web app

Click Run

![image](https://github.com/nibinkjoseph/Mlops-Project-2-Azure-Devops/assets/63180074/8edf26f0-c009-4d95-875b-73f6c3c5aa67)








==================================================================================

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









