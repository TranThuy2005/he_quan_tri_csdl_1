# Bài tập môn Hệ quản trị cơ sở dữ liệu-TEE560, Lớp: 59KMT
Họ tên: Trần thị Thùy

Lớp: K59KMT.K01

MSSV: K235480106070

## BÀI TẬP #

1. Download và cài đặt SQL Server 2025, phiên bản Developer

   Link tải: https://www.microsoft.com/vi-vn/sql-server/sql-server-downloads 

   Chọn phiên bản *SQL Server 2025 Developer*

   Không chọn Azure (nặng, ko dùng đến), các tính năng mở rộng khác (feature) chọn tất cả   

   Cài đặt với 2 kiểu login (Mixed Mode): Windows Authentication (nhớ **Add Current User**) và SQL Server Authentication (username mặc định là **sa**, chỉ cần nhập mật khẩu **123** , nhớ nhập 2 chỗ: Enter password và Confirm password)
<img width="1920" height="1080" alt="Screenshot 2026-04-09 153517" src="https://github.com/user-attachments/assets/6505ea39-36db-429a-97fb-0f745aafa7d0" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 153531" src="https://github.com/user-attachments/assets/1733cbb9-cca9-45b8-a54b-0b8702d0213f" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 153539" src="https://github.com/user-attachments/assets/4a6aaa83-5a7b-458b-8d22-a998595835d0" />
   
<img width="1920" height="1080" alt="Screenshot 2026-04-09 153547" src="https://github.com/user-attachments/assets/da4538ec-8cb6-48cf-af4b-98718192c47b" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 153602" src="https://github.com/user-attachments/assets/712dfe3e-569c-449c-9533-0760f591243d" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 153939" src="https://github.com/user-attachments/assets/0639b04c-5dd9-443b-a7e3-aa007218839b" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 154027" src="https://github.com/user-attachments/assets/60f5802e-39b8-4ade-a836-6a88cad9b31b" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 154153" src="https://github.com/user-attachments/assets/f5e8faa8-42da-41f3-8ab4-cca37370f2d3" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 154241" src="https://github.com/user-attachments/assets/a5a8b62a-b293-4853-bc1d-61306004e0d3" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 154302" src="https://github.com/user-attachments/assets/d100852f-127b-4072-bf28-ae6eef351a08" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 154649" src="https://github.com/user-attachments/assets/c470d33e-84ff-4a20-af70-61f69e50c9bb" />

<img width="1920" height="1080" alt="Screenshot 2026-04-09 155030" src="https://github.com/user-attachments/assets/456ecb6c-161d-454c-8125-cf77c6bcae2d" />


2. Cấu hình cho SQL Server làm việc ở cổng động (Dynamic Port), TCP: enable+active yes cho 127.0.0.1, chọn cổng động là 3xxxx với xxxx là **4 số cuối của mã số sv**, (nếu cổng này đã mở sẵn trước đó bởi 1 ứng dụng khác thì chọn cổng là 4xxxx hoặc 5xxxx
<img width="1920" height="1080" alt="Screenshot 2026-04-11 213214" src="https://github.com/user-attachments/assets/6c155c67-8aae-40e8-a796-b2b85afd20dc" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213225" src="https://github.com/user-attachments/assets/64d2c3e4-026b-44d4-853d-a57ed066c439" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213247" src="https://github.com/user-attachments/assets/fa11bada-d36a-43db-a83e-55622f3b4b12" />


3. Kiểm tra xem service SQL Server có đang running và mở đúng cổng đã chọn hay không?

   Sử dụng lệnh trên cmd: *netstat -ano | findstr LISTENING* để liệt kê các cổng mà máy tính đang mở,

   Nếu thấy dòng: **TCP    0.0.0.0:xxxxx**  với xxxxx là cổng đã chọn ở bước 2 là OK.

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213349" src="https://github.com/user-attachments/assets/604ac208-ce68-4052-aac9-b80716018b6d" />


4. Cài đặt SQL Server Management Studio

   Link tải SSMS: https://learn.microsoft.com/en-us/ssms/install/install
<img width="1920" height="1080" alt="Screenshot 2026-04-09 213934" src="https://github.com/user-attachments/assets/01cdd19a-bf78-4453-9ec3-67ac232b81b9" />


5. Chạy phần mềm ssms để Đăng nhập vào SQL Server bằng 2 cách: Windows Authentication và SQL Server Authentication.

   Servername: localhost,xxxxx  (với xxxxx là cổng đã chọn ở bước 2)
<img width="1920" height="1080" alt="Screenshot 2026-04-11 213446" src="https://github.com/user-attachments/assets/22f267e9-0cc7-466e-967e-f6f5aa623ea0" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213458" src="https://github.com/user-attachments/assets/11a24765-e19c-478f-9a99-69e319020b58" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213515" src="https://github.com/user-attachments/assets/c825849b-af8d-4636-afc6-706d76157455" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213531" src="https://github.com/user-attachments/assets/42f10408-137f-4e6e-9a79-87262931c039" />


6. Sử dụng giao diện đồ hoạ của ssms: Tạo cơ sở dữ liệu mới (create database) với tên tuỳ ý, chọn Path (nơi lưu trữ db) cho file lưu dữ liệu và file lưu log ở ổ đĩa khác với ổ C. mở path đã chọn xem 2 file đã tạo ra.
<img width="1920" height="1080" alt="Screenshot 2026-04-11 213605" src="https://github.com/user-attachments/assets/9ddf730c-14c9-46f4-bb85-ab73756e7145" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 213624" src="https://github.com/user-attachments/assets/2966a107-d904-474f-8ead-4314e80b7da9" />


7. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng dữ liệu (create and design table) với tên bảng tuỳ ý, có các trường dữ liệu phù hợp với dữ liệu của file [data mẫu (CSV)](./svtnut.csv?raw=true), với Khoá chính (Primary Key) là trường **masv**
<img width="1920" height="1080" alt="Screenshot 2026-04-11 222046" src="https://github.com/user-attachments/assets/3dff1b13-b9fb-4f80-ae22-910370cc2830" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 222104" src="https://github.com/user-attachments/assets/fbcbba0f-1bf7-4d6e-9da4-301adcf73cc3" />


8. Sử dụng giao diện đồ hoạ của ssms: Tìm cách import dữ liệu từ file mẫu vào trong bảng vừa tạo.
<img width="1920" height="1080" alt="Screenshot 2026-04-11 222046" src="https://github.com/user-attachments/assets/4fed6900-5407-4ba1-a277-54ae14715848" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 222123" src="https://github.com/user-attachments/assets/0e7896bb-e1a5-4fc1-ae72-be28dde34bad" />


9. Mở cửa sổ mới để gõ lệnh trong ssms: GÕ lệnh để kiểm tra xem số dòng của bảng dữ liệu sau khi import, kết quả ok sẽ khoảng 12020 dòng.
<img width="1920" height="1080" alt="Screenshot 2026-04-11 222303" src="https://github.com/user-attachments/assets/5e6c2dfa-bc0d-4cbd-9fb5-b5a85ccf2f6f" />


10. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để thêm (insert) 1 row vào bảng, với dữ liệu là thông tin cá nhân của sv đang làm bài (mỗi sv sẽ luôn khác nhau ở bước này).
<img width="1920" height="1080" alt="Screenshot 2026-04-11 222331" src="https://github.com/user-attachments/assets/054fa4a6-8821-4979-9a9b-1323ed9c0a60" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 222734" src="https://github.com/user-attachments/assets/12bf8e0d-6163-4ef6-aef5-b1b96b86438a" />

11. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để cập nhật(update) trường noisinh thành 'Sao Hoả' cho những dòng có noisinh và diachi đều là NULL.
<img width="1920" height="1080" alt="Screenshot 2026-04-11 222615" src="https://github.com/user-attachments/assets/aa1b903a-75ba-4572-aa9c-635585494df1" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223043" src="https://github.com/user-attachments/assets/1c158132-e9ee-4107-b44b-36a0ceaea814" />

12. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng **SaoHoa** gồm những sinh viên có nơi sinh ở 'Sao Hoả', keyword gợi ý: sử dụng 1 câu lệnh: SELECT + INTO

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223119" src="https://github.com/user-attachments/assets/f633066b-1ce1-47b1-a019-878dd34aaed7" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223152" src="https://github.com/user-attachments/assets/f5e4b5b4-8b15-48e9-b520-6404e2eabb41" />

13. Trong cửa sổ mới để gõ lệnh: Gõ lệnh xoá (delete) trong bảng **SaoHoa** những sinh viên cùng họ với em, vd em họ nguyễn thì xoá những sv họ nguyễn.

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223235" src="https://github.com/user-attachments/assets/5880ad76-4eb8-4b92-b91f-00dfd5acdae9" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223253" src="https://github.com/user-attachments/assets/06c37920-0989-41f7-b09e-e4f3cb0676d7" />


14. Sử dụng giao diện đồ hoạ của ssms: Xuất toàn bộ kết quả của các bước 6,7,8,9,10,11,12,13 ra file **dulieu.sql** , keyword gợi ý: sử dụng tính năng GEN SCRIPT struct+data cho database

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223412" src="https://github.com/user-attachments/assets/502a6a2d-b23f-4d0f-ae16-a261e71ad084" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223428" src="https://github.com/user-attachments/assets/1d805f27-8153-4d35-8dcc-398055bad621" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223526" src="https://github.com/user-attachments/assets/8b2d104e-1b8e-4a94-bf3f-8e95e183991b" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223542" src="https://github.com/user-attachments/assets/41d1a1e3-c3b4-43e9-86d8-74c65fce1731" />

15. Sử dụng giao diện đồ hoạ của ssms: Xoá csdl đã tạo, sau khi xoá thành công, kiểm tra tại path (path chọn ở bước 6) xem còn tồn tại 2 file của bước 6 không?
<img width="1920" height="1080" alt="Screenshot 2026-04-11 223644" src="https://github.com/user-attachments/assets/0df9c9e7-c4f1-4110-9a93-8351c547e244" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223651" src="https://github.com/user-attachments/assets/5044e5da-0e5b-4960-9a49-c11a3151e8b3" />

16. Tạo cửa sổ mới để gõ lệnh: mở file **dulieu.sql** của bước 14, chạy toàn bộ các lệnh này. REFRESH lại cây liệt kê các database => kiểm chứng kết quả được tạo ra tương đương với các bước 6,7,8,9,10,11,12,13.
<img width="1920" height="1080" alt="Screenshot 2026-04-11 223725" src="https://github.com/user-attachments/assets/59d13bb9-94b0-4aee-9e2e-ddd5e3ff2b04" />

<img width="1920" height="1080" alt="Screenshot 2026-04-11 223808" src="https://github.com/user-attachments/assets/2b131b26-ee1c-4cd6-b4df-cbdb21c7e14c" />

17. upload file **dulieu.sql** lên github repository của em (repository mà em đang edit file README.md)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d4366577-1e0f-49a6-9e4f-61e47a175fee" />

