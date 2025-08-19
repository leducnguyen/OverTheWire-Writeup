# LV13 🖼️ Image Upload Bypass  

When accessing this challenge, the page displayed a **message** along with the buttons **choose file** and **upload file**:  
<img width="1920" height="481" alt="image" src="https://github.com/user-attachments/assets/a1cbc247-3b13-4514-a5e0-57b7abd49459" />  
The page hinted that only **image files** (≤ 1KB) are allowed. Checking the **View Source Code**, I found this line:  
<img width="1113" height="923" alt="image" src="https://github.com/user-attachments/assets/88e8ecaa-2a05-4bd3-98fe-3969345f8363" />  
👉 This revealed the use of `exif_imagetype($_FILES['uploadedfile']['tmp_name'])`, meaning the server checks the **first bytes (magic header)** to ensure the file is a real image.  

I uploaded a normal image and intercepted the request using **Burp Suite**:  
<img width="1920" height="371" alt="image" src="https://github.com/user-attachments/assets/63c12417-3a18-45bc-834e-17df246dc7a6" />  
<img width="1495" height="537" alt="image" src="https://github.com/user-attachments/assets/63a1da44-d2cb-41aa-a6e1-e1c8bcd4ede7" />  
✔️ This confirmed that validation is based on the **image header bytes**.  

To bypass this, I crafted a file starting with valid image header bytes but injected a malicious PHP payload:  
```php
<?php system('cat /etc/natas_webpass/natas14'); ?>
I renamed the file with a .php extension and uploaded it successfully:
<img width="1486" height="754" alt="image" src="https://github.com/user-attachments/assets/5f65d683-4c5f-4c67-a67c-8eb9bc9505bc" />
Then I visited the uploaded file path shown in the server response, and the PHP code executed, revealing the password:
<img width="1432" height="468" alt="image" src="https://github.com/user-attachments/assets/6dde28e7-9871-4d42-959e-b414a5677a85" />

The password for Natas14 is:

```
z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ
```
