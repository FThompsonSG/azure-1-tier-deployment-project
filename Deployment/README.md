# 2 Tier Deployment Process

## Manual Testing
1. Once I had launched a virtual machine, the first step would be to SSH in and run commands manually to verify that each command works individually. As this was a two tier deployment it meant that I had to plan the order of virtual machine launches slightly differently to previously when I had just the one tier to focus on. Without a working database virtual machine I would have no way to properly test that the application was connected and working as intended so I started with the database and then moved on to the application. I could test the connection manually and then confirm at this stage that the application was running by entering my IP address and port into my browser.

## Script Testing
2. When the individual commands have been verified I moved on to the next level of automation which was writing a script for each virtual machine. I would start by creating the script files in the command terminal, planning the steps and order of the script with comment annotations and then moving my manual commands into the scripts including messages printed to the console to make my life easier with regards to keeping track of developments. To guarantee the scripts were idempotent I would run them repeatedly to be sure this could happen with no ill effects. A blocker than I experienced during this phase took the form of the repository being cloned with no contents which happened as a result of the application script being rerun whilst the application was still running meaning the repository could not be fully accessed. This was resolved by including a stop command in my script prior to the clone command. Once again I ensured that everything was working by checking the app in my web browser.

## User Data Testing
3. Once I was satisfied that the script level of automation had been achieved, I moved on to user data. User data is script that you provide to the virtual machine prior to launching and the script is executed as part of the machines initialisation. This script only runs once. By providing my working scripts as user data to the new instances of virtual machines, once they were initialised, I was able to access my working app via the browser without having to SSH in to the virtual machine at all.

## AMI Instance Testing
4. Finally once those instances were verified and running successfully, I created a Amazon machine images of those instances. Amazon machine images or AMIs are like a snapshot or a template of a virtual computer that you can use as a starting point to create new virtual machines. It is like a pre-configured package that includes an operating system, software, and any additional configurations you need. In simple terms, an AMI is a blueprint for creating virtual machines in AWS. So by creating an AMI of these working instances, I could in future launch instances from those AMIs with everything required up and running and only a few lines of user data required when launching as opposed to requiring the entire script. In this case the database virtual machine required no user data whatsoever and the application virtual machine only required five commands to ensure it ran as intended.

## Apache Reverse Proxy
5. Also as part of the application script that I wrote, I included what is referred to as a proxy reverse server which we utilised so that the port would not be required when wanting to access the app via the browser and simply providing the IP address at this stage would redirect to the correct port automatically.

NB. From this project one of my most prominent takeaways is that it is crucial to remember is that each time a virtual machine is stopped and started it is assigned a new IP address. When providing the user data for the application instance this was integral as it requires the up to date IP of the database instance otherwise it cannot connect.