🔐 **Level 17**

After logging into the server, we find two files: **`passwords.new`** and **`passwords.old`**. The hint says the correct password is in the **`.new`** file, and the two files differ only slightly.  
<img width="407" height="769" alt="image" src="https://github.com/user-attachments/assets/2c976c99-38cb-4edd-bced-f437a639096a" />

To locate the exact difference, we use the `diff` command 🔎 to compare the two files:  
```bash
diff passwords.old passwords.new
<img width="443" height="85" alt="image" src="https://github.com/user-attachments/assets/dc4f131f-26e8-4e94-8fe2-fad2e85dd6bc" />
The differing line reveals the password 🔑:
```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```
