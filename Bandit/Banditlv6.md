🔐 **Level 6**

After accessing the server, we start by using the `ls` command 📂 to list the files in the current directory:  
<img width="633" height="446" alt="image" src="https://github.com/user-attachments/assets/f6ea07b2-0a91-4e9c-a215-6a94e237490f" />

To locate the password, we know the target file belongs to **user `bandit7`**, has **group `bandit6`**, and its size is exactly **33 bytes**. We use the `find` command with these conditions, and redirect error messages to `/dev/null` to avoid unnecessary output:  

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
This returns the location of the hidden password file:
<img width="623" height="55" alt="image" src="https://github.com/user-attachments/assets/722fd682-a272-4dae-8612-e0659e555667" />

Finally, using cat 📖 on the file, we obtain the password 🔑:

✨ Password:
```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
