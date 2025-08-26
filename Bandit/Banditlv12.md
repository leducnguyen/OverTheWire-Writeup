🔐 **Level 12**

After running the `ls` command 📂, we find a file named **`data.txt`**. Using `cat` 📖 shows strange unreadable content:  
<img width="574" height="407" alt="image" src="https://github.com/user-attachments/assets/614ef955-148c-4e22-82d2-aa1949fe2959" />

This indicates the file is **encoded in binary/hex**. To work with it, we copy the file into a temporary directory such as `/tmp/mybandit12` for editing. Since it’s encoded, we rename it with the `.bin` extension and use the `file` command 🔎 to identify its type:  
<img width="633" height="279" alt="image" src="https://github.com/user-attachments/assets/c1e99a39-2c59-485a-a15b-48790531f270" />

Using the `xxd` command, we can convert the hex dump into a binary file. Then, we repeatedly check the file type and rename it with the proper extension (using `mv`) so it can be extracted correctly. For example, when the file is recognized as a **tar archive** 📦 or a **bzip2 compressed file** 🗜️, we rename and extract it accordingly:  
<img width="639" height="373" alt="image" src="https://github.com/user-attachments/assets/c1e99a39-2c59-485a-a15b-48790531f270" />  
<img width="631" height="377" alt="image" src="https://github.com/user-attachments/assets/d055b9d8-372a-45d2-8a01-dcb4106e74be" />

After going through multiple layers of extraction 🎭, we finally uncover the file containing the password 🔑:  

✨ **Password:**  
```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
