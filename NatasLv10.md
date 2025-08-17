# LV10 🕵️ Filtering & Grep Trick  

At the beginning of this challenge, the webpage displayed a **message** with an **input field**:  
<img width="1920" height="551" alt="image" src="https://github.com/user-attachments/assets/7e416801-fbda-4c64-bc71-fd23729ced35" />  

👉 Just like in **LV9**, entering input shows lines containing the given character.  
But this time, when I clicked **View Source Code**, the page revealed the following:  
<img width="1471" height="901" alt="image" src="https://github.com/user-attachments/assets/f94aced9-f699-4b9f-95bb-f3e490a8bcca" />  

Here we can see that **special characters** (`; | &`) are blocked by a regex filter, so we cannot end the command using `;` like in the previous level.  

---

## 🔎 Exploitation Strategy
Instead of chaining commands, the idea is to let **grep** search across **multiple files** at once:  
- `dictionary.txt` (default file)  
- `/etc/natas_webpass/natas11` (the hidden password file)  

So the trick is to provide a pattern + file path:  

Z /etc/natas_webpass/natas11


This runs as:  
```bash
grep -i Z /etc/natas_webpass/natas11 dictionary.txt
```
✨ Result

The password immediately appeared:

UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk

<img width="1904" height="819" alt="image" src="https://github.com/user-attachments/assets/a6d59051-9b53-4f62-9ee3-278c4a78ebff" />
