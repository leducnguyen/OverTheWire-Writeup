# LV8 🧩  

When accessing the webpage, I once again encountered a **secret message** along with an **input field**, looking quite similar to **LV6**:  
<img width="1920" height="452" alt="image" src="https://github.com/user-attachments/assets/0551de9b-9e0d-459b-bbca-1b66b0815311" />  

👉 Clicking **View Source Code**, the browser redirected me to the file **index.html**:  
<img width="1365" height="856" alt="image" src="https://github.com/user-attachments/assets/ea978b72-09f9-4d3b-a4b9-ad563cfd8177" />  

Inside, I noticed an **encode function** applied through multiple layers:  
`bin2hex(strrev(base64))`  

So, I decoded step by step 🔍:  
- First, **convert from Hex**.  
- Then, **reverse the encoded string**.  
- Finally, **decode from Base64**.  

After processing all steps, I obtained a **new string**:  
<img width="1541" height="878" alt="image" src="https://github.com/user-attachments/assets/8d1d3df1-30f4-4cfc-a101-58aea86c2e32" />  

✨ This looked like the **secret**, so I pasted it into the input field and clicked **Submit**.  
<img width="1907" height="454" alt="image" src="https://github.com/user-attachments/assets/d76eab77-e2c4-40d7-9bc0-fa33168c9261" />  

And finally, the **challenge key** appeared 🎉:  
ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t
