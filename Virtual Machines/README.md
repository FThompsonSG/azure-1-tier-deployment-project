- [Azure Virtual Machines](#azure-virtual-machines)
  - [Creating a Virtual Machine](#creating-a-virtual-machine)
  - [Connecting to your Virtual Machine via SSH](#connecting-to-your-virtual-machine-via-ssh)


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

## Connecting to your Virtual Machine via SSH

1. From the 'Virtual Machines' page, Select your VM and then hit 'Connect'.
  ![Connect Tab](<VM Images/Screenshot 2024-01-02 170008.png>)

2. Now Choose 'Native SSH'.
  ![Native SSH](<VM Images/Screenshot 2024-01-02 170230.png>)

3. Next, we need to enter the path of our Private Key File in order to generate a custom ssh command.
  - We can do this by specifying the path to our key file here:
  - For example `"~/.ssh/name_of_file.pem"`
  ![SSH Tab](<VM Images/Screenshot 2024-01-02 170255.png>)

- We can Now copy the command that has been generated.

4. Open a CLI (Command Line Interface), I use Git Bash, and paste the command that we generated in the previous step.
   ![Bash Image](<VM Images/Screenshot 2024-01-02 215752.png>)

5. You will be asked to confirm connection, type 'yes' and press enter
   ![Confirm fingerprint](<VM Images/Screenshot 2024-01-02 220145.png>)

6. You are now logged into the VM and can start to execute commands.
   ![SSH Successful](<VM Images/Screenshot 2024-01-02 220410.png>)
