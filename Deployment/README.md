# 1 Tier Deployment Automation Process

## Manual Testing
1. Once we had launched a virtual machine, the first step would be to SSH in and run commands manually to verify that each command works individually. We could test the connection manually and then confirm at this stage that the application was running by entering our IP address and port into our browser.

## Script Testing
1. When the individual commands have been verified we moved on to the next level of automation which was writing a script. We would start by creating the script files in the command terminal, planning the steps and order of the script with comment annotations and then moving our manual commands into the scripts including messages printed to the console to make our lives easier with regards to keeping track of developments. To guarantee the scripts were idempotent we would run them repeatedly to be sure this could happen with no ill effects. Once again we ensured that everything was working by checking the app in our web browser.

## User Data Testing
1. Once we were satisfied that the script level of automation had been achieved, we moved on to user data. User data is script that you provide to the virtual machine prior to launching and the script is executed as part of the machines initialisation. This script only runs once. By providing our working script as user data to the new instance of a virtual machine, once they were initialised, we were able to access my working app via the browser without having to SSH in to the virtual machine at all.

## VM Image Instance Testing
1. Finally once our instance were verified and running successfully, we created a virtual machine image of the instance. Virtual machine images are like a snapshot or a template of a virtual computer that you can use as a starting point to create new virtual machines. It is like a pre-configured package that includes an operating system, software, and any additional configurations you need. In simple terms, a VM image is a blueprint for creating virtual machines. So by creating an image of these working instances, we could in future launch instances from those images with everything required up and running and only a few lines of user data required when launching as opposed to requiring the entire script. In this case the application virtual machine only required five commands to ensure it ran as intended.

## Apache Reverse Proxy
5. Also as part of the application script that we wrote, we included what is referred to as a proxy reverse server which we utilised so that the port would not be required when wanting to access the app via the browser and simply providing the IP address at this stage would redirect to the correct port automatically.