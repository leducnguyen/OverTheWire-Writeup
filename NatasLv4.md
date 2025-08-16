## # LV4 🔐
In this challenge, we receive a message:
![image](https://github.com/user-attachments/assets/e1f63eea-d470-4d7e-befe-232550886b05)
The line `"while authorized users should come only from http://natas5.natas.labs.overthewire.org/"` tells us that we will only be authorized if our request originates from that link.
Therefore, I used **Burp Suite** to intercept the **REQUEST**:
![image](https://github.com/user-attachments/assets/fb0daf31-d3a7-40fe-9e43-77d80df0e074)
Then I **Sent the Request to Repeater** to modify it, and added the following line:
```http
Referer: http://natas5.natas.labs.overthewire.org/
```
to the request headers to "spoof" the source of access.
![image](https://github.com/user-attachments/assets/bb3fbbbe-fa99-4540-bfb2-fa044aaf412a)
🎉 **The flag appeared** in the response — success!
