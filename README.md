
Challenge 1

E chưa biết làm huhu :((

-----------------------------------------------------------------------------------------------------------------------

Challenge 2


![c2_1](https://user-images.githubusercontent.com/39523988/115667191-15d7f200-a335-11eb-8031-092148f94b92.png)



Ngay khi vừa vào, trang web đã hiện ra phần source. Chúng ta cùng phân tích.
Ở bài này các đối số đầu vào sẽ là contrai và congai.

Nhìn lướt qua đoạn code, ta chú ý ngay tới lệnh if xuất flag.



![c3_4](https://user-images.githubusercontent.com/39523988/115668883-2d17df00-a337-11eb-90db-17dc8f3d1ba4.png)

Code được viết bằng PHP, cộng thêm việc các kết quả được hash bằng md5, ý tưởng ở đây là exploit bằng type juggling do hàm so sánh có sử dụng "==".
Để đơn giản nhất, chúng ta sẽ tìm các đối số nhập vào để khi hash sẽ ra dạng "0exxxxx".


![c2_2](https://user-images.githubusercontent.com/39523988/115667713-ad3d4500-a335-11eb-832c-8d9cea21ad25.png)

Bắt đầu từ câu lệnh if này, hàm ctype_alpha() có nhiệm vụ kiểm tra xem trong chuỗi có character nào thuộc alphabet hay không.
Vì thế ta sẽ tìm kiếm chuỗi nhập vào có chỉ gồm toàn chữ cái mà khi hash bằng md5 có dạng "0exxxxx"


![c2_3](https://user-images.githubusercontent.com/39523988/115668322-7fa4cb80-a336-11eb-83e2-6627716f1639.png)

Tiếp tục xuống lệnh if kế tiếp, ở đây hàm is_numeric() kiểm tra xem trong string có character nào thuộc dạng number hay không.
Với ý tưởng ban đầu, ta tìm string nhập vào gồm toàn chữ số mà khi hash sẽ cho dạng "0exxxxxxx".


![c2_5](https://user-images.githubusercontent.com/39523988/115670522-08bd0200-a339-11eb-91e4-85f06a27b0fa.png)

Sau một hồi tìm kiếm, ta sẽ sử dụng bảng trên.


![c2_6](https://user-images.githubusercontent.com/39523988/115670942-808b2c80-a339-11eb-8c12-57679b843334.png)


Voila! Và đây là kết quả.

![c2_7](https://user-images.githubusercontent.com/39523988/115671038-9b5da100-a339-11eb-97fb-dbfc0aacc819.png)

-----------------------------------------------------------------------------------------------------------------------

Challenge 3

![c3_1](https://user-images.githubusercontent.com/39523988/115671308-e677b400-a339-11eb-853f-2284b81b6176.png)

Mình đã thử qua một số kiểu SQLi, nhưng không cho lại kết quả gì. Nên ở đây mình sẽ cheat một chút, sử dụng tool dirsearch tìm các file ẩn trong domain =))).


![c3_2](https://user-images.githubusercontent.com/39523988/115672103-b846a400-a33a-11eb-85b3-d3061dd0e6a5.png)

Kết quả thu được


![c3_3](https://user-images.githubusercontent.com/39523988/115672325-f93eb880-a33a-11eb-9593-d9b6670d4073.png)

Check qua vài file thì bị Error 403 Forbidden, còn lại 3 file đáng chú ý.


![c3_4](https://user-images.githubusercontent.com/39523988/115672616-41f67180-a33b-11eb-803a-00b9d0350cc8.png)

/index.php và /index.php/login/ đưa ta quay lại trang chủ, tiếp tục thử file robots.txt.


![c3_5](https://user-images.githubusercontent.com/39523988/115672929-926dcf00-a33b-11eb-9448-bae5221218f1.png)

Dẫn tới một file khác, nhập vào URL xem sao.


![c3_6](https://user-images.githubusercontent.com/39523988/115673173-dd87e200-a33b-11eb-86e7-c5f17afda8fb.png)


Kết quả:
![c3_7](https://user-images.githubusercontent.com/39523988/115673285-fd1f0a80-a33b-11eb-9125-c754b44bc4e3.png)





