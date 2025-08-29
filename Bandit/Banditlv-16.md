🔐 **Level 16**

The hint suggests scanning ports **31000–32000** to find any open services. We run:  
```bash
nmap -p 31000-32000 localhost
```
<img width="584" height="203" alt="image" src="https://github.com/user-attachments/assets/82362026-7155-4151-b118-6c4bd79a408e" />
The scan shows five open ports. We then try each with SSL using:
```
ncat --ssl localhost <port>
```
At port 31790, we submit the previous level’s password:
<img width="690" height="489" alt="image" src="https://github.com/user-attachments/assets/6f36c891-59ef-4fc4-8654-059bb4b8f7cd" />

The service returns an RSA private key 🔑 (used to authenticate to the next level). We save this key into a file (e.g., in a writable directory like /tmp) using an editor such as nano, then set strict permissions so SSH will accept it:

```
nano /tmp/bandit17.key     # paste the RSA key here, save & exit
```
```
chmod 600 /tmp/bandit17.key
```
Now we SSH into bandit17 using that key:

```
ssh -i /tmp/bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
```
<img width="866" height="760" alt="image" src="https://github.com/user-attachments/assets/293f174d-0d60-4b81-8a38-1f1ed75aebb6" />
Finally, we read the password for bandit17:

```
cat /etc/bandit_pass/bandit17
```
✨ Password:

```
EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
```
