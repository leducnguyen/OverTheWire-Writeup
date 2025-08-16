# LV3 🚩
When accessing the web page, I received the same message as in the previous challenge:
![image](https://github.com/user-attachments/assets/b7633acf-6520-4df8-ba03-cd7cf009f1d5)
I tried clicking **view page source** to inspect the source code, just like before:
![image](https://github.com/user-attachments/assets/21c42908-c653-4b78-8739-b4d0963ebc90)
This time, it wasn’t as easy to find a hidden file in the source like in the last challenge, so I tried probing some commonly hidden files and directories:
- `/robots.txt`
- `/s3cr3t/`
- `/admin/`
- `/hidden/`
- `/backup/`
- `/test/`
- `/index.html.bak`
When I tried **/s3cr3t/**, I discovered this:
![image](https://github.com/user-attachments/assets/5ff3712b-7dc7-4653-b974-7a796f2813fc)

🖱️ I clicked on `users.txt`, and received the password:
<img width="1192" height="291" alt="image" src="https://github.com/user-attachments/assets/3ffba1ec-7b9f-4120-9876-a9af2ea84be9" />
