# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên: Nguyễn Thái Hoàng**
- **Lớp:CNTT3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS): Windows**

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
PS D:\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\access.log | Select-String "ERROR" > .\logs\error_report.txt
PS D:\starter-kit\trung-tam-tieng-anh> Get-Content .\logs\error_report.txt -Head 2
```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)

```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
PS D:\starter-kit\trung-tam-tieng-anh> (Get-Content .\logs\access.log | Select-String "WARNING").Count
PS D:\starter-kit\trung-tam-tieng-anh> (Get-Content .\logs\payment.log | Select-String "ERROR").Count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log:4
ERROR trong payment.log:3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS D:\starter-kit\trung-tam-tieng-anh> .\auto_warning.ps1

```

### Nội dung file logs/warning_report.txt

```text
Script: auto_warning.ps1
 Tac gia: Nguyá»…n ThĂ¡i HoĂ ng
 Ngay tao: 21/10/2026 
=== CANH BAO THANH TOAN ===

2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
PS D:\starter-kit\trung-tam-tieng-anh> history

  Id CommandLine
  -- -----------
   1 cd D:
   2 cd .\starter-kit\trung-tam-tieng-anh\
   3 Get-Content .\logs\access.log | Select-String "ERROR" > .\logs\error_report.txt
   4 Get-Content .\logs\error_report.txt -Head 2
   5 Get-Content .\logs\error_report.txt -Head 2
   6 Get-Content .\logs\error_report.txt -Head 2
   7 (Get-Content .\logs\access.log | Select-String "WARNING").Count
   8 (Get-Content .\logs\payment.log | Select-String "chứa ERROR").Count
   9 (Get-Content .\logs\payment.log | Select-String "ERROR").Count
  10 (Get-Content .\logs\payment.log | Select-String "ERROR").Count
  11 .\auto_warning.ps1
  12 Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
  13 .\auto_warning.ps1
  
  Get-Content .\logs\access.log | Select-String "ERROR" >> .\logs\tong_hop_ngay2.txt; Get-Content .\logs\payment.log | Select-String "WARNING" >> .\logs\tong_hop_ngay2.txt
```

### Nội dung file logs/tong_hop_ngay2.txt

```text
=== TONG HOP ACCESS LOG ===



2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)



2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 5. Câu hỏi ngắn

- **a)Lệch > dùng để ghi đề nên nội dụng trước, khiến mất dữ liệu đã lưu, lệnh >> dùng để ghi nối tiếp, không gây mất nội dung cũ**
- **b)Nếu dùng lệnh > thay cho >> ở đoạn ERROR sẽ khiến mất dòng chữ === TONG HOP ACCESS LOG ===**
- **c)Khi chạy script, không phải máy nào cũng có user giống đường dẫn đã ghi khi sử dụng đường dẫn tuyệt đối, khi dùng đường dẫn tuyệt đối sẽ khiến cho script không thể chạy. Nên dùng đường dẫn tương đối để chạy script mà không gây lỗi**

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
