# SOC-Lab
Walkthrough of my Active Directory lab with Splunk log collection and brute force detection.
The purpose of this lab was to gain hands on experience within the security field of IT, particularly carrying out attacks on my AD joined target machine and analysing them in a Splunk server.
## Important note❗
All of the Virtual Machines should be on the same network so that they can communicate with other. To do this, I created a NAT Network on Virtualbox with the Network IP of 192.168.10.0, I then appklied this to all the Machines involved.
## Tools used 
1. Windows Server (DC) (Sysmon and Splunk Universal Forwarder was also installed on this machine)
2. Windows client target machiene (Domain joined) (Sysmon and Splunk Universal Forwarder was also installed on this machine))
3. Splunk Server - to log and analyse events
4. Ubuntu machine to carry out a brute force attack, using the tool crowbar
5. Atomic red team on my client machine to carry out test attack/event via a MITRE attack code.
## Objectives 🎯
1. Test brute force detection using crowbar
2. Forward detailed Windows Event logs into Splunk with the help of Sysmon to collect the logs on the machine and Splunk Universal Forwarder to send them over.
## Key Takeways 💡
1. Crowbar requires xfreerdp for RDP Brute Force
2. Failed logins generate Event ID 4625 whereas a successfull login generated 4624
3. Sysmon and Universal forwarder work together for detailed logs to be sent to the Splunk server
4. Splunk can detect Brute Force via a simple query
   
