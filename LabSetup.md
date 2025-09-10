# Lab Setup Overview 
## Splunk Server
1. I installed Splunk server from Ubuntu's site and created a VM for it in VirtualBox
2. To update and upgrade its repositories, I ran the command sudo apt-get update && sudo apt0get upgrade
3. 


## Active Directory Domain Controller
I will not go into detail about setting up AD as I have a project solely for that already
1. I installed Windows Server and configured Active Diretory Domain Services role in Server Manager. To do this you would click on Add roles and features, then select Active Diretory Domain Services and install.
2. After it has installed, you would click "Promote this server to a Domain Controller" and this is where you can configure a new forest and enter details such as your domain name.
3. After you have configured, you can then press install in which after your machine would reboot, you would then have a Domain Controller configured where you can create users, Organisational groups etc via Active Directory Users and Computers.
4. In this lab, I created 2 users and the one which was attacked was Terry Smith, with the username of tsmith
- <img width="188" height="43" alt="image" src="https://github.com/user-attachments/assets/26f30cb6-158a-42c6-98af-7ea7f8ebb12e" />
## Windows domain joined client
1. I joined this client via the about page in settings and "Rename this PC (advanced)"
2. Then put in the name of your domain and if the network settings are set properly and the client and DC is on the same network, the computer should join and prompt for a restart. 
3. Now this PC is under control and you can sign in with your created accounts.

    
