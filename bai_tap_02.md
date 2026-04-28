### Họ tên: Trần Thị Thùy
### MSSV: K235480106070
### Lớp K59KMT.K01

# Bài làm
### Phần 1: Thiết kế và Khởi tạo Cấu trúc Dữ liệu
- Tạo database QuanLyKhachSan
<img width="1920" height="1080" alt="Screenshot 2026-04-27 205659" src="https://github.com/user-attachments/assets/25c92de9-b808-4a56-a0eb-c40fb8fdde7c" />

- Sau khi tạo database xong
<img width="1920" height="1080" alt="Screenshot 2026-04-27 205714" src="https://github.com/user-attachments/assets/d1a5146d-4828-46cb-88a1-bc1fcc59201f" />

- Tạo 3 bảng có quan hệ với nhau
- Tạo bảng KhachHang
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210134" src="https://github.com/user-attachments/assets/62f34748-f21d-4338-b505-fedc6a331543" />

- Sau khi có bảng khachHang

PK: KhachHangId

CK: Điểm tích lũy >=0
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210155" src="https://github.com/user-attachments/assets/60f9b318-f08e-4bf9-b077-2d91f265e72e" />

- Tạo bảng Phong
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210250" src="https://github.com/user-attachments/assets/def5b8e9-86f6-4cbb-8d6c-70846da3b5f8" />

- Sau khi có bảng Phong

PK: PhongId

CK: GiaPhong > 0

TrangThai chỉ được 1 trong 3 giá trị ('Trống', 'Đã thuê', 'Bảo trì')
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210304" src="https://github.com/user-attachments/assets/a0fe6d5c-48cd-408b-b6f3-41121fd536bd" />

- Tạo bảng trung gian
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210622" src="https://github.com/user-attachments/assets/b490432f-0a66-41e6-a9f0-f35677d01207" />

- Sau khi có bảng trung gian

PK: DatPhongId

FK: KhachHangId -> KhachHang 

PhongId -> Phong
   
CK: TongTien >= 0          

NgayTraPhong -> NgayNhanPhong
    
<img width="1920" height="1080" alt="Screenshot 2026-04-27 210410" src="https://github.com/user-attachments/assets/0265d845-3e6a-4239-b799-a7ab52f8842e" />

### Phần 2: Xây dựng Function
- Một số loại hàm có sẵn phổ biến 

String Function (chuỗi)

Ví dụ: LEN(), UPPER(), LOWER()

Number Function (số)

Ví dụ: ROUND(), ABS()

Date Function (ngày tháng)

Ví dụ: GETDATE(), DATEDIFF()

Aggregate Function (tổng hợp)

Ví dụ: SUM(), AVG(), COUNT()

System Function (hệ thống)

Ví dụ: @@VERSION, SUSER_NAME()

- Một số hàm mà em thấy đặc sắc

GETDATE() – Hàm lấy ngày giờ hiện tại

Có thể dùng để tính ngày thuê phòng
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211110" src="https://github.com/user-attachments/assets/d65a1a6d-439e-41fc-86cd-1837ff379981" />

DATEDIFF() – Hàm tính khoảng cách thời gian

Có thể tính số ngày mà khách ở lại khách sạn
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211135" src="https://github.com/user-attachments/assets/fab9c6e2-fc7e-46a6-8fbd-7f710e2ffa00" />

LEN() – Độ dài chuỗi
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211154" src="https://github.com/user-attachments/assets/c9ffcfd8-75d2-47eb-907a-dbe88bfa67e1" />

ISNULL() – Xử lý NULL

dùng để tránh lỗi tính toán 
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211211" src="https://github.com/user-attachments/assets/7bfdb5b3-4656-49e1-8816-d6a6d4522dfb" />

+ Hàm tự viết

Scalar Function

dùng để tính toán đơn lẻ, ví dụ như tính tiền

Tạo hàm 
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211248" src="https://github.com/user-attachments/assets/92d18ebc-a58f-4b94-8642-22c36e3e84ed" />

Sử dụng
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211317" src="https://github.com/user-attachments/assets/fffff538-2aab-4a6d-97a5-c1f7f75c7326" />

Inline Table-Valued Function

dùng để lọc dữ liệu cơ bản

Tạo hàm 
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211351" src="https://github.com/user-attachments/assets/57491933-edcb-483a-b053-17e9dc4ec64c" />

Sử dụng hàm vừa tạo
<img width="1920" height="1080" alt="Screenshot 2026-04-27 211944" src="https://github.com/user-attachments/assets/1ec5c4e3-aa94-4dcb-8fc9-2cb51eb27683" />
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212031" src="https://github.com/user-attachments/assets/791aa946-a978-4886-8f00-68f0f866679c" />
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212044" src="https://github.com/user-attachments/assets/a88f4356-3dca-4b75-8ec5-98b113be83e7" />

Multi-statement Table-Valued Function

Trả về danh sách đặt phòng kèm:

Số ngày ở

Tổng tiền tính lại

Tạo hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212134" src="https://github.com/user-attachments/assets/97855e40-b8af-448a-8357-f924d06d52b2" />

sau khi có hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212157" src="https://github.com/user-attachments/assets/24e31a81-aa6f-4605-b5f5-2a8994852b10" />

### Phần 3: Xây dựng Store Procedure
Một số vài system sp mà em tìm hiểu được:

sp_help: Dùng để xem cấu trúc thông tin bảng
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212546" src="https://github.com/user-attachments/assets/47c8ca6d-890d-4847-87fe-a691f7dfe382" />

sp_columns: Dùng để xem chi tiết cột
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212609" src="https://github.com/user-attachments/assets/f648aded-497a-4b50-8c13-020b79a017fa" />

sp_databases: Dùng để liệt kê tất cả database
<img width="1920" height="1080" alt="Screenshot 2026-04-27 212652" src="https://github.com/user-attachments/assets/8af68dac-9719-4956-b432-db8611c04535" />

1. Viết store Procedure INSERT có kiểm tra

Yêu cầu:

Thêm đặt phòng nhưng:

Ngày trả phải > ngày nhận

Phòng phải đang “Trống”

Tạo hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213207" src="https://github.com/user-attachments/assets/5b9f6cf1-a24a-4a86-aa25-c747e4c56eeb" />

Sử dụng hàm

Lúc này khi chưa thêm dữ liệu, trạng thái của tất cả là trống
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213451" src="https://github.com/user-attachments/assets/fac3c9b3-0259-4235-adde-68055eb21adf" />

Sau khi Insert
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213537" src="https://github.com/user-attachments/assets/fec1162f-7b31-4030-a286-9438995c54aa" />
bảng sẽ thay đổi từ trống sang đã thuê
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213554" src="https://github.com/user-attachments/assets/03a042a2-a93d-4ce4-a7e4-6e8c047b9ad6" />

2. Viết store Procedure có OUTPUT

Yêu cầu:

Tính tổng tiền đặt phòng -> trả về qua OUTPUT

Tạo hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213633" src="https://github.com/user-attachments/assets/ef4338cb-206f-4bef-a8b2-a04d8126badb" />

Sử dụng hàm vừa tạo
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213700" src="https://github.com/user-attachments/assets/4f5e1057-22b3-488d-8705-2c2b8d2a3017" />

3. Viết store Procedure trả về Result Set (JOIN nhiều bảng)

Yêu cầu:

Hiển thị:

Tên khách

Phòng

Giá

Ngày thuê

Tổng tiền

Tạo hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213727" src="https://github.com/user-attachments/assets/5b06d5c4-52a2-4877-b78f-4581096434c9" />

Sử dụng hàm
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213751" src="https://github.com/user-attachments/assets/fcc6eaec-21fc-420e-8c30-22e5d865c653" />

### Phần 4: Trigger và Xử lý logic nghiệp vụ

Trigger: Tự động cập nhật trạng thái phòng

Khi có đặt phòng (DatPhong)

Phòng phải chuyển sang “Đã thuê”

Trigger trên bảng A (DatPhong)
<img width="1920" height="1080" alt="Screenshot 2026-04-27 213914" src="https://github.com/user-attachments/assets/d7dcddaf-2fe3-4d42-a168-99cec8716aa3" />

sau khi insert dữ liệu cho bảng A(DatPhong)
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214010" src="https://github.com/user-attachments/assets/1ba7f171-0161-4865-8a08-aa1b5ef9902a" />

Bảng A thêm dữ liệu vào bảng
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214342" src="https://github.com/user-attachments/assets/2c8d35aa-d093-4ec5-98b0-e4a0b2648bb8" />

Viết Trigger cho bảng B(Phong)
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214507" src="https://github.com/user-attachments/assets/b28fa768-b91f-4c5e-a1be-51295627c5cb" />

Sau khi chạy Trigger bảng B (Phong), Thì dữ liệu lúc nãy insert sẽ update tự động vào bảng B, Phòng được đặt sẽ được thay đổi từ 'trống' chuyển thành 'Đã thuê'
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214544" src="https://github.com/user-attachments/assets/fdf8e418-acdc-4eea-a91c-7538bb7d6c73" />

Nhận xét:
Sau khi insert bảng A(DatPhong), trigger 1 sẽ chạy và update vào bảng Phong. Sau khi update bảng Phong trigger 2 sẽ chạy và update vào bảng DatPhong, sau khi update bảng datPhong xong trigger 1 lại chạy và quay lại từ đầu. Vòng lặp cứ lặp đi lặp lại một cách vô hạn mà không có điểm dừng.
Điều này cho thấy cần thiết kế trigger cẩn thận, tránh cập nhật qua lại giữa các bảng mà không có điều kiện kiểm soát.

### Phần 5: Cursor và Duyệt dữ liệu

Bài toán sử dụng CURSOR

Với mỗi bản ghi trong bảng DatPhong:

Tính lại Tổng tiền = số ngày * giá phòng

Cập nhật vào cột TongTien

Viết CURSOR
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214809" src="https://github.com/user-attachments/assets/31635a6e-68b8-4755-a3bc-d5a068cbd9db" />

Không dùng CURSOR
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214852" src="https://github.com/user-attachments/assets/35e54d22-589c-4a3b-bfb4-30addce12656" />

So sánh tốc độ giữa việc sử dụng CURSOR và không sử dụng CURSOR

Tốc độ khi sử dụng CURSOR
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214932" src="https://github.com/user-attachments/assets/eb48ea62-2614-4f95-8064-5e020645c1ec" />

Tốc độ khi không sử dụng CURSOR
<img width="1920" height="1080" alt="Screenshot 2026-04-27 214953" src="https://github.com/user-attachments/assets/4402098f-66a5-42e5-89a5-a3a55d86739c" />

Nhận xét:
Cách không dùng CURSOR nhanh hơn vì SQL Server tối ưu cho xử lý tập dữ liệu thay vì xử lý từng dòng

Bài toán mà chỉ CURSOR mới giải quyết được

Gửi thông báo riêng cho từng khách hàng:

Nếu ở > 5 ngày -> VIP

Nếu < 5 ngày -> thường

In thông báo khác nhau từng người
<img width="1920" height="1080" alt="Screenshot 2026-04-27 215148" src="https://github.com/user-attachments/assets/f936af05-6e4f-46a5-9030-626b04d71f07" />
