# BÀI TẬP VỀ NHÀ 03: THIẾT KẾ VÀ CÀI ĐẶT CSDL QUẢN LÝ CẦM ĐỒ
## Môn học: Hệ quản trị CSDL. Lớp 59KMT. GV: Đỗ Duy Cốp
### Họ tên sinh viên: Trần Thị Thùy
### Lớp: K59KMT.K01
### MSSV: K235480106070
-----------
## Nhiệm vụ 1: Thiết kế CSDL

Vẽ sơ đồ ERD: thể hiện rõ thực thể, thuộc tính, khóa chính, khóa ngoại. 

Chuyển sơ đồ thành các bảng (Lưu ý chuẩn hóa tối thiểu mức 3NF).

- Sơ đồ thực thể liên kết trong sql
<img width="1920" height="1080" alt="Screenshot 2026-05-08 180722" src="https://github.com/user-attachments/assets/2aa46fc1-4784-411a-8c80-0c994e52817d" />

- Hình vẽ sơ đồ ERD của bài
<img width="1920" height="1080" alt="Screenshot 2026-05-08 182937" src="https://github.com/user-attachments/assets/ea5a17f5-5b04-46f0-ac1a-93ff54b6a007" />

---------------

## Nhiệm vụ 2: Cài đặt SQL
- Event 1: Đăng ký hợp đồng mới (Vay tiền)
  
  Tạo database QuanLyCamCo và tất cả bảng dữ liệu
<img width="1920" height="1080" alt="Screenshot 2026-05-08 164657" src="https://github.com/user-attachments/assets/d1aaeab6-9d8e-4a0f-b816-835b8bf59db3" />

 Viết Store Procedure tiếp nhận hợp đồng: Lưu thông tin khách hàng, danh sách tài sản 
(kèm giá trị định giá), số tiền vay gốc và thiết lập 2 mốc Deadline1, Deadline2.

SQL Server không truyền mảng trực tiếp vào Procedure nên ta cần tạo kiểu dữ liệu Table Type cho danh sách tài sản
<img width="1920" height="1080" alt="Screenshot 2026-05-08 183742" src="https://github.com/user-attachments/assets/76981ba1-92aa-4719-9036-6724283089dc" />

Viết Stored Procedure đăng ký hợp đồng mới 
<img width="1920" height="1080" alt="Screenshot 2026-05-08 183645" src="https://github.com/user-attachments/assets/40fe1e3e-98c4-45e7-b04d-74a7d826b9ed" />

Ví dụ sử dụng Procedure
Tạo danh sách tài sản
<img width="1920" height="1080" alt="Screenshot 2026-05-08 183855" src="https://github.com/user-attachments/assets/19f4d5fa-86b1-4ed2-91fc-545da5d2c194" />

Gọi Procedure
<img width="1920" height="1080" alt="Screenshot 2026-05-08 184703" src="https://github.com/user-attachments/assets/efa17ed0-0ed1-4ec2-9fd0-566446dfd985" />
<img width="1920" height="1080" alt="Screenshot 2026-05-08 184807" src="https://github.com/user-attachments/assets/3555a5ac-5e03-4cb4-88a3-0cb979e2637c" />

- Event 2: Tính toán công nợ thời gian thực viết Function fn_CalcMoneyTransaction(TransactionID, TargetDate) để tính số tiền phải trả của TransactionID này cho đến ngày TargetDate

Viết Function fn_CalcMoneyTransaction(TransactionID, TargetDate)

Function này tính:

số tiền phải trả của 1 giao dịch/hợp đồng

tại thời điểm TargetDate

Viết function
<img width="1920" height="1080" alt="Screenshot 2026-05-08 185743" src="https://github.com/user-attachments/assets/24ac9058-1f7f-4931-97ae-2e732bf55951" />

Sử dụng function vừa tạo
<img width="1920" height="1080" alt="Screenshot 2026-05-08 190009" src="https://github.com/user-attachments/assets/b1b1618b-4d90-40ea-94b4-3b5e845ad4cb" />

Viết một Function fn_CalcMoneyContract(ContractID, TargetDate) để tính tổng số tiền 
khách(ContractID) phải trả (Gốc + Lãi đơn + Lãi kép) tính đến ngày TargetDate.
<img width="1920" height="1080" alt="Screenshot 2026-05-08 185927" src="https://github.com/user-attachments/assets/bc7c5329-8c06-40be-8e6e-b77636b360b5" />

Sử dụng fn
<img width="1920" height="1080" alt="Screenshot 2026-05-08 190124" src="https://github.com/user-attachments/assets/0a80a404-3bde-48fd-a934-34a2ed67c8e7" />

- Event 3: Xử lý trả nợ và hoàn trả tài sản
Viết Store Procedure xử lý khi khách mang tiền đến: Nếu tài sản đã bị thanh lý (sau Deadline 2 và có cờ IsSold): Thông báo không thu tiền, không trả đồ.
<img width="1920" height="1080" alt="Screenshot 2026-05-08 190728" src="https://github.com/user-attachments/assets/9bf759bc-2faa-4c63-bbe9-c7cc2eec5dc3" />

Sử dụng Store Procedure vừa tạo
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191236" src="https://github.com/user-attachments/assets/85506f39-7d65-4024-a6d5-ae67e08960ad" />
Dữ liệu bảng vừa cập nhập

Nếu tài sản chưa bị thanh lý: Tính tổng nợ, trừ số tiền khách trả vào hệ thống.

Nếu chưa trả hết tiền gốc+lãi: cập nhật trạng thái hợp đồng thành “Đang trả góp”
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191251" src="https://github.com/user-attachments/assets/e26b01f0-f8cf-47ca-b87e-b2e3c5604d8a" />
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191423" src="https://github.com/user-attachments/assets/8d942b30-5997-4b98-bee6-fb0641b27d02" />
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191453" src="https://github.com/user-attachments/assets/711a8f1a-d04d-4137-8cc4-397b33b4dceb" />

- Event 4: Truy vấn danh sách nợ xấu (Nợ khó đòi)

Viết function để truy vấn danh sách nợ xấu
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191608" src="https://github.com/user-attachments/assets/64b4a88d-a297-4d78-af79-26dfeb7c6d47" />

sau khi truy vấn sql sẽ xuất ra 1 danh sách các khách hàng đã quá Deadline 1 mà chưa thanh toán. 
Gồm: Tên KH, Số điện thoại, Số tiền vay gốc, Số ngày quá hạn, Tổng tiền phải trả hiện tại (đến ngày hiện tại), tổng số tiền phải trả sau 1 tháng nữa.

- Event 5: Quản lý thanh lý tài sản

Viết Trigger tự động chuyển trạng thái hợp đồng sang "Quá hạn (nợ xấu)" sau khi hợp đồng đang ở trạng thái "Đang vay" mà ngày vượt quá Deadline 1.
<img width="1920" height="1080" alt="Screenshot 2026-05-08 191833" src="https://github.com/user-attachments/assets/ea75e3dc-201b-4c9d-99c7-8283d1fab875" />

Viết Trigger tự động chuyển trạng thái tài sản sang "Sẵn sàng thanh lý" sau khi hợp đồng đang ở trạng thái "Quá hạn (nợ xấu)" mà ngày vượt quá Deadline 2.
<img width="1920" height="1080" alt="Screenshot 2026-05-08 192055" src="https://github.com/user-attachments/assets/40179599-c1af-4dab-872b-534d4f3421de" />

Viết Trigger tự động chuyển trạng thái tài sản thành “Đã bán thanh lý” sau khi trạng thái của hợp đồng chuyển sang "Đã thanh lý".
<img width="1920" height="1080" alt="Screenshot 2026-05-08 192136" src="https://github.com/user-attachments/assets/715ea5db-1ac2-4cae-a300-02b47881019f" />

Hợp đồng tự update
<img width="1920" height="1080" alt="Screenshot 2026-05-08 193913" src="https://github.com/user-attachments/assets/c7925320-d01d-4e83-9ad6-8849635d9d57" />
