🔐 **Level 15 (SSL/TLS)**

Similar to the previous task, we connect to **localhost**, but this time the service on **port 30001** is protected by **SSL/TLS**. Therefore, we use **OpenSSL** to establish the connection:

```bash
openssl s_client -connect localhost:30001
```
<img width="647" height="257" alt="image" src="https://github.com/user-attachments/assets/a8331783-b36d-4b7e-991e-b91878342ff3" />
When prompted, we paste the previous level’s password, and the service returns the next password 🔑:

<img width="337" height="80" alt="image" src="https://github.com/user-attachments/assets/5353783f-9c4d-4b81-85ff-cb902d1de7a3" />
✨ Password for Bandit16:

```
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```
