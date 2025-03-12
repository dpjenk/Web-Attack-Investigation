WEB ATTACK INVESTIGATION

Objective

Investigate a web server access log after the web server was attacked.

Skills Learned

- Proficiency in analyzing and interpreting a web server access log.
- Ability to recognize brute force and code injection web attack signatures and patterns.
- Development of critical thinking and problem-solving skills in cybersecurity.

Steps

1) Opened the web server access log and discovered the attacker was using Nikto (an automated scanning tool) for web reconnaissance. Also, the numerous HTTP requests within a matter of seconds indicate the use of an automated tool.

Figure 1:

<img width="659" alt="WA1" src="https://github.com/user-attachments/assets/0a744ab9-9e03-44cc-9b36-9b3132866ad7" />

2) The attacker attempted to access various names of directories. The attacker encountered status code 404 which indicates the directories did not exist. This represents a brute force attack.

Figure 2:

<img width="659" alt="WA6" src="https://github.com/user-attachments/assets/6d82c0eb-5a88-4250-9dc0-95a66044bf40" />

3) The attacker tried another brute force attack to submit a login form via POST request. The attacker received a 200 response which indicates that the result of the action was transmitted to the message body. However, this resulted in a lack of success.

Figure 3:

<img width="664" alt="WA2" src="https://github.com/user-attachments/assets/7e5b7600-d9ef-4564-b774-fd6d8da5f7cd" />

4) In line 12,546 the attacker finally received a 302 status code which redirected to the portal page. In line 12,548 a status code of 200 and a response size of 23,369 indicates the brute force was successful.

Figure 4:

<img width="664" alt="WA3" src="https://github.com/user-attachments/assets/1630ff6e-3663-4b62-bd06-f0209e29a55e" />

5) The attacker then uses code injection beginning in line 12,553 with the first payload being "whoami". In line 12,556 and following the payload is persistent "net user hacker asd123 /add".

Figure 5:

<img width="655" alt="WA4" src="https://github.com/user-attachments/assets/8a5c9c62-7188-434e-aefd-d7205fd1a3b6" />

Figure 6:

<img width="661" alt="WA5" src="https://github.com/user-attachments/assets/4a84ccfa-0c43-425b-b7ab-d76087e6ec0e" />





