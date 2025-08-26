🔐 **Level 5**

First, we use the `ls` command 📂 to list the files in the home directory:  
<img width="486" height="429" alt="image" src="https://github.com/user-attachments/assets/3ca79397-6808-4592-a026-b01e05ef86cb" />

Next, we run the `file` command 🔎 to check the type of each file:  
<img width="614" height="374" alt="image" src="https://github.com/user-attachments/assets/2e60b338-310a-4830-a9ab-c73bbecb1976" />

From the instructions, we know the file containing the password has a **size of 1033 bytes** and is detected as a regular file.  
👉 So, we use the `find` command with the correct conditions:  

```bash
find . -type f -size 1033c
```
This finds the target file:
<img width="493" height="78" alt="image" src="https://github.com/user-attachments/assets/57273424-76e0-4263-acf8-3431ab702696" />

Finally, using cat 📖 on the file reveals the password 🔑:

✨ Password:
```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
