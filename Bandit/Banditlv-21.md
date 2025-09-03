 **Level 21**

The hint suggests investigating scheduled jobs in **`/etc/cron.d/`**. Using `ls` 📂, we list the files there:  
<img width="1335" height="38" alt="image" src="https://github.com/user-attachments/assets/5797f940-1301-46a6-b42e-6d10c8ac0aee" />

Inside, we find a script named **`job_bandit22.sh`**. Let’s inspect it with `cat`:  
<img width="699" height="55" alt="image" src="https://github.com/user-attachments/assets/9c22f0aa-8257-4a58-bd57-53af9c5d69f3" />

This shows that at reboot, another script is executed from a specific path. We continue by checking that file with `cat`:  
<img width="661" height="104" alt="image" src="https://github.com/user-attachments/assets/10c1ba57-79b8-46ed-931a-19c68dbc705f" />

The script reveals the password for the next level 🔑.

✨ **Password for Bandit22:**  
```
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```
