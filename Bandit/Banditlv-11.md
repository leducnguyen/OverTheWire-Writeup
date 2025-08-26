🔐 **Level 11**

After running the `ls` command 📂, we find a file named **`data.txt`**. Using `cat` 📖 to read it:  
<img width="566" height="79" alt="image" src="https://github.com/user-attachments/assets/964ab6e5-e603-47ed-9ae8-42c8363d55f0" />

The output shows a strange encoded string. Based on the challenge hint, we know it requires a **ROT13 substitution cipher** 🔄, which shifts each letter by 13 positions in the alphabet.  

We can decode it using the `tr` command:  

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```
This reveals the correct password 🔑:
<img width="537" height="91" alt="image" src="https://github.com/user-attachments/assets/7e1a05e0-171f-4687-a929-088a550286be" />
```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
