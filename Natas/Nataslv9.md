# LV9 ⚡ Command Injection  

When accessing the webpage, I saw a **small message** along with an **input field**:  
<img width="1920" height="440" alt="image" src="https://github.com/user-attachments/assets/99657c49-05c3-4b2a-b2be-43d51fe96566" />  

👉 After entering a random input, the page returned a list of strings containing the entered character.  
This behavior suggested a possible **Command Injection** vulnerability:  
<img width="1920" height="631" alt="image" src="https://github.com/user-attachments/assets/726f7f70-1389-43d1-a266-9f121457dfd7" />  

🔎 I also noticed the text **"view src code"** in the bottom-right corner, so I clicked on it and discovered that the challenge uses the PHP function **`passthru`**, which executes **Linux system commands**:  
<img width="1382" height="819" alt="image" src="https://github.com/user-attachments/assets/87ed3776-7c2f-43e4-9791-e7598afb2eb7" />  

To exploit this, I injected the following payload to terminate the current command and execute **cat** on the password file:  

test; cat /etc/natas_webpass/natas10
Simply put, the above command is substituted directly into the place where the key is attached to the previous passthru command.

<img width="1919" height="1008" alt="image" src="https://github.com/user-attachments/assets/db5211c6-fd40-4e4f-9748-761106034c50" />  

✨ And the **password appeared** 🔑:  

