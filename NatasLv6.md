# LV6 🔐  

When accessing the website, I received a **"secret"** message along with an input field:  
<img width="1920" height="329" alt="image" src="https://github.com/user-attachments/assets/82d41570-24e9-4b0e-a126-c4b59bfa47a7" />  

👉 Trying with a random string, the site responded with: **Wrong secret** ❌  
<img width="1920" height="368" alt="image" src="https://github.com/user-attachments/assets/5fee7c01-50ee-48c0-8e35-ea7547ec0779" />  

So, I clicked on **View Page Source** 🖥️ and found the file `index.html`:  
<img width="1516" height="786" alt="image" src="https://github.com/user-attachments/assets/50367ecf-0ee5-44b1-9d7c-f5634438e645" />  

🔎 I noticed a strange message line that looked like a **directory path**.  
By appending it to the URL, I discovered the hidden **secret**:  
<img width="1138" height="192" alt="image" src="https://github.com/user-attachments/assets/49e5b2d9-1eea-4e30-8e64-0c89424d78b9" />  

✨ Finally, I took the revealed **secret**, entered it into the input field, and obtained the **challenge key** 🔑:  
<img width="1561" height="457" alt="image" src="https://github.com/user-attachments/assets/c34a25e2-38f4-4ae6-bfd1-bb87dac7cdcb" />  

---

> ### 📝 Takeaway / Lesson Learned 💡  
- Always inspect the **page source** (`Ctrl + U`) for hidden clues.  
- Sometimes secrets are **stored in directories** or files that can be accessed directly.  
- Don’t rely only on the visible UI – check behind the scenes! 👀  
