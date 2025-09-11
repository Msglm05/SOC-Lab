# Attacks 🎯
❗In this section, is important that all of the virtual machines involved in this lab to be up and running for connectivity between the systems such that the operations carry out successfully, such as the attack, the logs being forwarded to splunk, accessing splunk etc. 
1. Now that the attacking machiene is in the same network and is equipped with its attacking tool, the attack can take place. As disussed, in this example I used a tool called crowbar which is a brute force tool and I specifically targeted the Remote Desktop service (RDP) that I made available in the target machine.
2. On the Ubuntu machine (attacking machine) I created a file called passwords.txt which contained common passwords in it, including the password of the victim user that I created in Active Directory which made a total of 21 passwords (I kept it on the smaller side so that not too many logs are generated). This file was then saved under my Desktop/ad-project directory and this is where the command was ran.
   <img width="1273" height="173" alt="Screenshot 2025-09-10 094136" src="https://github.com/user-attachments/assets/b76fbbde-2d11-44d8-89a8-7f9de3ca1907" />
3. As can be seen in the picture the attack was successful and was able to RDP brute force into the victim acount.
4. 
