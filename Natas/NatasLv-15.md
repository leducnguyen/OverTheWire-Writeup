# LV15 🧪 Boolean-Based Blind SQL Injection  

When accessing the page, it showed a short message and an input to enter a username:  
<img width="1920" height="487" alt="image" src="https://github.com/user-attachments/assets/3ff43517-f748-4b9e-90be-8e67ff5681df" />  
Clicking **View Source Code** revealed the backend logic:  
<img width="1364" height="873" alt="image" src="https://github.com/user-attachments/assets/28edf902-536e-48a1-b315-bf2fef87c1db" />  
The PHP code executes a query and only returns whether the user exists or not, which means this is a **boolean-based blind SQLi** challenge. Additionally, the comment showed the database schema:  

```
CREATE TABLE users (
username varchar(64) DEFAULT NULL,
password varchar(64) DEFAULT NULL
);
```

This confirms that every user has an associated password, so the goal is to extract the password of **natas16**. I injected into the username field with:  

```
natas16" AND SUBSTRING(password,1,1)='a'-- "
```

and repeated this by replacing `a` with different characters 🔄 and advancing the substring position, checking the boolean response each time. If the page said **“This user exists”**, the condition was **true ✅** and that character was correct.  

⚡ To speed things up I wrote a **Python brute-forcer** 🤖 to iterate over all positions and characters until the full password was recovered:  
<img width="943" height="533" alt="image" src="https://github.com/user-attachments/assets/7fbd6e09-96d5-4438-b537-9fb788a7eaf1" />  

Eventually the full key appeared 🎉:  
<img width="731" height="267" alt="image" src="https://github.com/user-attachments/assets/309caeec-029a-4d8a-9867-9324e9620f16" />  

🔑 The password for **Natas16** is:  

```
hPkjKYviLQctEW33QmuXL6eDVfMW4sGo
```
