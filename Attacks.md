# Attacks 🎯
❗In this section, is important that all of the virtual machines involved in this lab to be up and running for connectivity between the systems such that the operations carry out successfully, such as the attack, the logs being forwarded to splunk, accessing splunk etc. 
1. Now that the attacking machiene is in the same network and is equipped with its attacking tool, the attack can take place. As disussed, in this example I used a tool called crowbar which is a brute force tool and I specifically targeted the Remote Desktop service (RDP) that I made available in the target machine.
2. On the Ubuntu machine (attacking machine) I created a file called passwords.txt which contained common passwords in it, including the password of the victim user that I created in Active Directory which made a total of 21 passwords (I kept it on the smaller side so that not too many logs are generated). This file was then saved under my Desktop/ad-project directory and this is where the command was ran.
   <img width="1273" height="173" alt="Screenshot 2025-09-10 094136" src="https://github.com/user-attachments/assets/b76fbbde-2d11-44d8-89a8-7f9de3ca1907" />
3. As can be seen in the picture the attack was successful and was able to RDP brute force into the victim acount.
4. To get more of an insight, I installed Atomic Red Team on my windows client to carry out a simulation attack with the aid of the MITRE framework, the command can be seen below.
<img width="1071" height="81" alt="Screenshot 2025-09-10 095505" src="https://github.com/user-attachments/assets/e61db757-63d9-41e7-8b9f-3475c655764e" />
5. Once installed, the folder for it shows under the C drive, and specifically the 'atomics' folders is used wchich references codes of attacks from the MITRE framework (Enterprise Matrix) which can then be used to execute a simulation attack via powershell, one example can be seen below in which T1136.001 was used which is creating a new user. The last screenshot is from the MITRE Framework (Enterprise Matrix)
<img width="943" height="715" alt="Screenshot 2025-09-10 100639" src="https://github.com/user-attachments/assets/1de7d72b-ce79-4bce-a890-bf94785df0ff" />
<img width="326" height="209" alt="image" src="https://github.com/user-attachments/assets/8b055aa3-cecf-4739-ab62-44d1f614e873" />

6. Next we will see the logs produced from these attacks on the splunk server.

