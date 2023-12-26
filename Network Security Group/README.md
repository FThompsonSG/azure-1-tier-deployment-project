# Network Security Groups

## Creating a Network Security Group

1. Log in to portal.azure.com and select 'Network Security Groups'.
   ![NSG Icon](<NSG-Images/Screenshot 2023-12-23 235948.png>)
- You can also use the search bar if you don't see it in this menu.

2. Select 'Create', Choose your 'Resource Group', give your network a name and change the region, I used '(Europe) UK West', Then press 'Next'.
   ![NSG Settings](<NSG-Images/Screenshot 2023-12-24 000519.png>)
   
3. Your NSG is now created, choose 'Go to Resource' to view.
   ![NSG Created](<NSG-Images/Screenshot 2023-12-24 000847.png>)

4. Select 'Inbound Security Rules' to Add new rules.
   ![Inbound Rules](<NSG-Images/Screenshot 2023-12-24 000943.png>)

5. From here, choose 'Add' to add a new rule.
   ![Inbound Rules Screen](<NSG-Images/Screenshot 2023-12-24 001006.png>)

6. We need to allow ssh traffic from my IP on port 22, so that we can  ssh into (login to) our vm's, we do that by setting the following options: 
   ![SSH Rule](<NSG-Images/Screenshot 2023-12-24 001108.png>)

7. Press 'Add' again and set the following for HTTP traffic on port 80:
   ![HTTP Custom Rule](<NSG-Images/Screenshot 2023-12-24 001522.png>)

8. And next we need to add a rule to allow traffic on port 5000, since our application runs on this port:  
   ![Custom 5000 Rule](<NSG-Images/Screenshot 2023-12-24 001544.png>)

10. That's It, Our Network Security Group is Complete. We can now start to create Virtual Machines.
   