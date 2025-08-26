🔐 **Level 8**

After logging into the server, we run `ls` 📂 to display the available files:  
<img width="373" height="461" alt="image" src="https://github.com/user-attachments/assets/a0cf6df0-c8a5-4d1a-93e6-9cf6cd66d27b" />

We find a file named **`data.txt`** containing many repeated strings. The task is to locate the unique one.  
👉 To do this, we can **sort** the file and then use **`uniq -u`** to filter out the line that appears only once:  

```bash
sort data.txt | uniq -u
```
This reveals the correct password 🔑:
<img width="413" height="436" alt="image" src="https://github.com/user-attachments/assets/8bc1ebeb-3c6d-42b7-89c1-70315d9733f9" />
✨ Password:
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
