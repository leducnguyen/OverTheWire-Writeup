🔐 **Level 18**

When connecting to the server, we immediately receive a logout message:  
<img width="607" height="562" alt="image" src="https://github.com/user-attachments/assets/fe207f77-ed39-49db-a410-77433ffcf591" />  
<img width="606" height="249" alt="image" src="https://github.com/user-attachments/assets/177b23f5-4e29-4ba9-b9dc-38965fd7b818" />

⚠️ This happens because the **`.bashrc`** file has been modified to force an exit as soon as we log in, preventing us from running commands interactively.

👉 To bypass this, we append the command directly after the `ssh` command so it executes before the forced logout. Specifically, we can run:  
```
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

This executes cat readme immediately upon connection, successfully revealing the password 🔑:
<img width="759" height="272" alt="image" src="https://github.com/user-attachments/assets/79a42fb5-e21e-41b6-9e70-1c8d739be978" />

✨ Password:
```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
