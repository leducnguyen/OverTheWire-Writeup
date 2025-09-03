🔐 **Level 20**

After logging in, we list the files with `ls` and find an executable named **`suconnect`**.  
Following the challenge hint, we must provide the **Bandit20 password** to a local TCP port and then have `suconnect` read from that port. First, we spin up a listener on **port 1234** that immediately sends the Bandit20 password:

```bash
echo -n '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -l -p 1234 &
```
The command above pipes the password to a backgrounded nc listener. Next, we run suconnect and point it to that port:
```
./suconnect 1234
```
<img width="1071" height="121" alt="image" src="https://github.com/user-attachments/assets/b5ebf216-f960-4226-9a79-707d9bd26f8b" />
suconnect fetches the password from the listener, validates it, and returns the next level’s password 🔑.

✨ Password for Bandit21:

```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```
