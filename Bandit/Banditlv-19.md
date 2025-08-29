🔐 **Level 19**

After connecting to the server and running `ls` 📂, we find a strange file:  
<img width="491" height="72" alt="image" src="https://github.com/user-attachments/assets/e58b9a1c-2c43-4ade-94da-a94bf127481f" />

Upon inspection, this file is an **executable binary with setuid permissions**, meaning it runs with the privileges of **bandit20** when executed.  

👉 We can leverage this to read the password file of bandit20 by running:  
```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```
This successfully outputs the next password 🔑:
<img width="525" height="56" alt="image" src="https://github.com/user-attachments/assets/82385b39-ad9e-4106-bb80-8076bff3f9ce" />

✨ Password for Bandit20:
```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```
