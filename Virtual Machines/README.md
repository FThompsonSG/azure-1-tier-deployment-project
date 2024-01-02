# Azure Virtual Machines

## Creating a Virtual Machine

1. Log into Azure and go to "Virtual Machines".

2. Select 'create', then 'Azure Virtual Machine'.
   ![Create VM](<VM Images/Screenshot 2023-12-24 002048.png>)

3. Select your 'Subscription', 'Resource Group', 'VM Name' and 'Region', then set 'Security Type' to 'Standard
   ![VM Settings](<VM Images/Screenshot 2023-12-24 002407.png>)

4. Now we need to select the correct image:
- Here we need to select 'See All Images', select the dropdown on ubuntu 22.04, and then choose 'Gen1' 
- We also need to select the correct Disk Size. Here we use 'Standard_B1s. 
   ![Image/Disk Option](<VM Images/Screenshot 2023-12-24 002439.png>)

5. Next, we need to select the key pair.
- We can either create a new one or select one that is already stored on Azure. In this example, we will generate a new key.
  ![Key Pair](<VM Images/Screenshot 2023-12-24 002531.png>)

6. Next we need to head to the 'Networking' tab:
- Here, select your 'Virtual Network' and 'Subnet', the 'Public IP' will be generated for us.
  ![Networking](<VM Images/Screenshot 2024-01-02 160009.png>)

7. Scroll down slightly and change 'NIC network security group' to 'Advanced':
- Then Select your 'Network Security Group' from the dropdown list. 
  ![NSG](<VM Images/Screenshot 2024-01-02 160641.png>)

8. Hit 'Review + create' and then hit 'Create' to create your Virtual Machine.
  ![VM Created](<VM Images/Screenshot 2024-01-02 161820.png>)

9. Now we need to download the 'Key File'
- Here, we need to select 'Download private key and create resource'
- The File Should be saved in your '.ssh' Folder.
  ![Key Pair Download](<VM Images/Screenshot 2023-12-24 003005.png>)

## Connecting to your Virtual Machine

