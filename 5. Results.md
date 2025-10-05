# Results of the attacks carried out - Logs produced 
1. Log into splunk by providing is IP address that was configured along with port 8000. Mine was 192.168.10.10:8000. Then click on search & reporting, then search for the index, the index I configured was endpoint, so the serach would be index=endpoint
2. Then Eventcode should be clicked on the left hand side to see the event code logs.
3. First, we will see the log of an unsucessfull brute force attempt from the previous shown crowbar command, and as you can see, my ubuntu machine username is displayed in the log, the event ID for failed logons are 4625. 
<img width="501" height="425" alt="Screenshot 2025-09-10 094840" src="https://github.com/user-attachments/assets/1b318d5c-bb2e-4587-95aa-4de1c9478b85" />
<img width="422" height="204" alt="Screenshot 2025-09-10 095011" src="https://github.com/user-attachments/assets/5f7462c1-1a41-44b6-a0dc-c3653d562a03" />

4. Next we will see the log for the sucessfull login which generates the EventID code of 4624
 <img width="501" height="409" alt="Screenshot 2025-09-10 094943" src="https://github.com/user-attachments/assets/97091118-d662-41fd-9878-83ad96f40c51" />
 <img width="453" height="290" alt="Screenshot 2025-09-10 095000" src="https://github.com/user-attachments/assets/5505ae88-e17e-4e72-aec4-b0b85930e597" />

6. Now we will see the log result of the simulation attack we ran via the use of Atomic Red Team of creating a new account as was seen in the attacks repo.
<img width="492" height="298" alt="Screenshot 2025-09-10 101132" src="https://github.com/user-attachments/assets/28730b46-a2b9-4987-8fa2-dabbc68d480e" />

And this was the end of this very insightful hands on project!
