# LV11 🔐 Cookie & XOR Decryption  

When starting this challenge, I was presented with a **message** and an **input field**:  
<img width="1919" height="551" alt="image" src="https://github.com/user-attachments/assets/06ee5539-0ae1-4870-a2a6-79e32b256d69" />  

👉 This input accepts a **Hex value**, which is then rendered as the page’s background color.  
The challenge also mentioned **Cookies**, so I inspected the cookies of the webpage:  
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a6905566-ae6f-4ace-bf8d-fcadf04f86c4" />  

Next, I clicked **View Source Code** to see the HTML file:  
<img width="1151" height="869" alt="image" src="https://github.com/user-attachments/assets/2c781618-0a6d-4fce-93c2-489e32ec9501" />  

Here, I found functions handling cookies, with operations involving **XOR**, **Base64**, and **JSON**.  

---

## 🔎 Analysis  

- The XOR formula is:  
ciphertext ^ key = plaintext
plaintext ^ key = ciphertext


- The objective is to craft a payload that will be encoded layer by layer for the cookie.  

I also noticed the following line in the source:  
<img width="665" height="129" alt="image" src="https://github.com/user-attachments/assets/90956af4-d989-448e-96c0-0634d559f1e4" />  

👉 This indicates we must set `"showpassword":"yes"` in the cookie data to reveal the flag.  

---

## 🚀 Exploitation Steps  

1. **Extract the XOR key**  
 - Decode the cookie value from **Base64** → ciphertext.  
 - XOR it with the known plaintext JSON:  
   ```json
   {"showpassword":"no","bgcolor":"#ffffff"}
   ```  
 - The repeated key was revealed as:  
   ```
   eDWo
   ```  

 <img width="1541" height="863" alt="image" src="https://github.com/user-attachments/assets/83cb7029-c1fe-4687-8047-88edd63a3e8c" />  

2. **Craft the malicious payload**  
 - Replace `"showpassword":"no"` with `"showpassword":"yes"`.  
 - Plaintext JSON becomes:  
   ```json
   {"showpassword":"yes","bgcolor":"#ffffff"}
   ```  

 - Encrypt with XOR using key `eDWo`.  
 - Encode the result in **Base64**.  

3. **Modify the Cookie**  
 - Set the cookie value to the newly encoded ciphertext.  
 - Reload the page.  

---

## ✨ Result  

The page displayed the password for the next level:  

```yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB```
