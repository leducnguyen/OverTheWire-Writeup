🔐 **Level 9**

We begin by running the `ls` command 📂 to list the available files:  
<img width="250" height="53" alt="image" src="https://github.com/user-attachments/assets/52ec7296-0e63-4f77-8409-0535e6002b13" />

Inside, we find a binary file. Using `cat` would produce unreadable output, so instead we use the `strings` command 🔎 to extract human-readable text. To narrow down the result, we pipe it through `grep =` to search for lines containing an equals sign (`=`):  

```bash
strings <filename> | grep =
```
This reveals the correct password 🔑:
<img width="577" height="296" alt="image" src="https://github.com/user-attachments/assets/1d538089-4892-42a2-9d9d-97e58358970a" />

✨ Password:

```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
