# Lab Setup Overview 
## Splunk Server
1. I installed Splunk server from Ubuntu's site and created a VM for it in VirtualBox
2. To update and upgrade its repositories, I ran the command sudo apt-get update && sudo apt0get upgrade
3. To change the IP to my desired one I configured its settings using sudo nano /etc/netplan/50-cloud-init.yaml
<img width="285" height="197" alt="image" src="https://github.com/user-attachments/assets/54c984d8-42eb-4422-9fc3-91a9fc81becb" />

5. After this sudo netplan apply was executed to apply these settings to the server.
6. On my host machiene, I went to splunk.com and installed Splunk Enterprise and installed the Linux .deb file and placed it in a desired folder.
7. To enable folder sharing, sudo apt-get install virtualbox-guest-additions-iso was installed along with guest-utils
8. On VirtualBox > Devices > Shared Folders > Shared Folder Settings > folder picture with + sign to add the folder in which splunk Enterprise was installed, I selected the options read only, auto mount and make permanent.
9. Rebooted the server and used the command sudo adduser mydfir vboxsf to add the user to the vboxsf group.
10. Created a new directory called share and mounted the shared file onto the this directory with the command, sudo mount -t vboxsf -o uid=1000,gid-1000 (name of the shared folder) share.
11. Changed directory into share in which the Splunk Enterprise installer was located and installed it using sudo dpkg -i splunk...(till the end).
Changed into the directory of where splunk was located under /opt/splunk and changed into the user splunk along with changing into the bin directory and ran ./splunk start to run the installer.
12. At the end you can set your admin username and password
13. To make sure splunk starts up every time VM reboots, exit out of the user splunk, change into bin and use sudo ./splunk enable boot-start -user splunk.

## Active Directory Domain Controller
I will not go into detail about setting up AD as I have a project solely for that already
1. Renamed to ADDC
2. Install Sysmon and Splunk Forwarder as seen in the client section.
3. I installed Windows Server and configured Active Diretory Domain Services role in Server Manager. To do this you would click on Add roles and features, then select Active Diretory Domain Services and install.
4. After it has installed, you would click "Promote this server to a Domain Controller" and this is where you can configure a new forest and enter details such as your domain name.
5. After you have configured, you can then press install in which after your machine would reboot, you would then have a Domain Controller configured where you can create users, Organisational groups etc via Active Directory Users and Computers.
6. In this lab, I created 2 users and the one which was attacked was Terry Smith, with the username of tsmith
7. 
- <img width="188" height="43" alt="image" src="https://github.com/user-attachments/assets/26f30cb6-158a-42c6-98af-7ea7f8ebb12e" />
## Windows domain joined client
1. Changed the PC name to Target-PC for easier log identification.
2. Set my desired staic IP of 192.168.10.100, Default gateway of 192.168.10.1 and DNS of 8.8.8.8 at first which then later chnaged to the DC's IP.
<img width="390" height="455" alt="image" src="https://github.com/user-attachments/assets/13777ab0-a7ac-45ad-8ae1-c74756df2719" />

3. Splunk universal forwarder was installed via splunk.com, once installed run the installer and select the option an on premises Splunk Enterprise Instance.
4. For the receiving indexer, this is the splunk server so put in its IP address with the default port of 9997 when recieving events. Once installed click finish.
5. Sysmon was also installed alongside Olafs config under his github account, locate sysmonconfig.xml > raw > right click save as.
6. Extract the installed sysmon folder, click on the file path and copy, then go to powershell with administrative privellegs and change into the filepath. Install the ./Sysmon64.exe, using the -i option to specify the config file, click enter and the installation would begin once agree is hit.
7. Important❗Splunk forwarder must be configured to send the specified logs to the splunk server by changing the inputs.conf file found in the C drive > Program Files > SplunkUniversalForwarder > etc > system > default, create that file under the local directory as editing under the default directory is not recommended as the inputs.conf file is there for backup. This will send the apprioprate logs to the to be created 'endpoint' file.
<img width="496" height="317" alt="image" src="https://github.com/user-attachments/assets/fae77052-743d-4e8f-ba3b-f22f335acb4b" />

8. Go to services and locate the splunk forwarder service, notice here the log on as option and change to local system account to ensure permissions will not affect the logs. Then restart the service as whenever the inputs.conf file is changed, the service has to be restarted.
## Configuring the Splunk Enterprise server 
1. Log in to the server via the web using its ip address with the port 8000.
2. Select settings > indexes and create an index called 'endpoint' so that the logs can be sucessfully forwarded to it.
3. Next enable the splunk server to receive data via settings > forwarding and recieving, under receive data > configure recieving > new recieving port and add the default port of 9997, then save. Now you can see data coming in from the client machine. <img width="639" height="127" alt="image" src="https://github.com/user-attachments/assets/623877d8-50a7-4d9c-a7f7-61afcd35155a" /> <img width="584" height="100" alt="image" src="https://github.com/user-attachments/assets/7b8dbea2-225a-41b3-9852-5de8b80f2d5b" />
## Ubuntu machine setup

 


 
    
