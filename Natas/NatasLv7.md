# LV7 🔎  

When accessing this challenge, I was presented with the following webpage:  
<img width="1759" height="359" alt="image" src="https://github.com/user-attachments/assets/dc82d09f-3f07-41c2-b9d8-e7cb055c209f" />  

👉 As usual, I right–clicked and selected **View Page Source**.  
There, I discovered a strange message related to a hidden file:  
<img width="1397" height="515" alt="image" src="https://github.com/user-attachments/assets/904df138-d1d1-457c-8c13-448d64ed784f" />  

The hint was clearly shown:  
`<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->`

So, I followed the given path to access the hidden file 🗂️:  
<img width="1636" height="411" alt="image" src="https://github.com/user-attachments/assets/ca418cf4-b3fb-40d1-b9ab-9a917a455b64" />  

✨ And just like that, the **key** appeared 🔑!  

---

> ### 📝 Takeaway / Lesson Learned 💡  
- Always check the **page source** – valuable hints are often hidden in HTML comments.  
- File paths like `/etc/natas_webpass/` may directly point to secret credentials.  
- Web challenges often simulate real server structures — don’t ignore **system file references** 👀.  
