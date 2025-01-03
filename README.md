# Azure Traffic Management | Hub & Spoke Network
This project is following the [lab for Microsoft's AZ 104 training](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_06-Implement_Network_Traffic_Management.md)

## Objective
Demonstrate how to implement traffic management in Azure using both an Azure Load Balancer and an Azure Application Gateway. The lab covers provisioning infrastructure via ARM templates, configuring a public load balancer to distribute requests across multiple VMs (layer 4), and then deploying an application gateway for advanced, layer 7 routing. By the end, traffic is split appropriately (e.g., images vs. videos), with health probes ensuring high availability and reliable application delivery.

### Skills Learned

- Azure
- Use a template to provision an infrastructure.
- Configure an Azure Load Balancer.
- Configure an Azure Application Gateway.

### Tools Used

- Azure Portal

### Prerequisites 

- Azure Subscription

## Steps
### Step 1 - Use ARM template to deploy infrastructure
- Go to Deploy a custom template in Azure Portal
- Load template file
- Load parameters file
- Fill out remaining parameters in Azure Portal

![image](https://github.com/user-attachments/assets/fe9bc0f3-0225-4916-97af-a33c7d3dde1b)


### Step 2 - Configure Azure Load Balancer

![image](https://github.com/user-attachments/assets/34addb0a-dce4-4f18-8bc1-f6236ebda9ac)


- In Azure Portal go to Load balancers and create a load balancer using the settings below

![image](https://github.com/user-attachments/assets/708ea4fc-f3fc-441d-9c9f-c7470eff4a7f)

- Add ip configuration for load balancer

![image](https://github.com/user-attachments/assets/98f5c67b-0fc0-4e76-a16b-4fb26506c907)


- Create public ip for the load balancer

![image](https://github.com/user-attachments/assets/04f6b126-c0a8-4d83-80c1-ae20cfc61394)

- Add VM's to the backend pool

![image](https://github.com/user-attachments/assets/e9e8ed22-b49b-4976-985c-bf737ef8d442)

- Create load balancing rule 

![image](https://github.com/user-attachments/assets/3852d7de-75bb-4b72-aa40-2f10f665a536)

- Review & Create load balancer

- Now we can navigate to the ip of the load balancer to verify it's working as expected

![image](https://github.com/user-attachments/assets/4f59b74a-5c64-4550-aee8-f6badde7b2eb)


### Step 3 - Configure Azure Application Gateway

![image](https://github.com/user-attachments/assets/33878a48-3016-49e8-aeef-d149d188776a)


- Create subnet for the application gateway

![image](https://github.com/user-attachments/assets/060fa175-63ae-497b-865c-d3507ef1f25e)

- Create application gateway

![image](https://github.com/user-attachments/assets/313c800d-4e1d-4a6e-bcb6-f2244d25a8b2)

- In front end setting create new public IP 

![image](https://github.com/user-attachments/assets/322ff0a6-2578-4781-920b-738cc41dc3f8)

- Add backend pool for vm 1 and vm 2, another backend pool for images and another for video

![image](https://github.com/user-attachments/assets/b6e52205-812c-49de-90e9-99ff2df06660)

- Add routing rule

![image](https://github.com/user-attachments/assets/9e4f3ad7-b07f-42a8-9aea-d081d5a2bbb3)

![image](https://github.com/user-attachments/assets/df3692f8-82a5-4b67-ad89-a99126da63a3)

- Add path based routing rules

![image](https://github.com/user-attachments/assets/e6d13b02-3c0c-40bf-9b27-b85205869ed5)

- Review and create application gateway

- Now go to the application gateway IP address and test that the /image and /video routing works as expected

![image](https://github.com/user-attachments/assets/8d8927f9-32f1-4eaa-a2f5-02899d725d6d)

![image](https://github.com/user-attachments/assets/95fea46f-299a-46a8-ac55-dd861a455990)

**Now that everything is working don't forget to delete the resources from Azure :) - easiest to delete the resource group used.**







