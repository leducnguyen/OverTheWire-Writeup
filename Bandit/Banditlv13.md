🔐 **Level 13**

After accessing the server, we notice there is a file named **`sshkey.private`** 🔑. To use it, we first transfer the file to our local machine using **`scp`**:  
<img width="925" height="335" alt="image" src="https://github.com/user-attachments/assets/6076537d-4fac-4a13-a1ce-3e8361861ea3" />

Next, we adjust the file permissions so that only the user can read/write it (otherwise SSH will refuse to use it). We do this with:  

```bash
chmod 600 sshkey.private
```
Then we connect to the Bandit14 account using the private key:
```
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```
✅ Successfully logged in as bandit14 🎉.

Finally, we read the password for the next level with:

```
cat /etc/bandit_pass/bandit14
```
✨ Password for Bandit14:

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```
