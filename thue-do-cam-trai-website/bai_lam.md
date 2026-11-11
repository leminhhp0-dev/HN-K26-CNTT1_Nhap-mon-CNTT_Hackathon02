# BÀI LÀM – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:Lê Hồng Minh**
- **Lớp:HN-K26-CNTT1**
- **Link repository:https://github.com/leminhhp0-dev/HN-K26-CNTT1_Nhap-mon-CNTT_Hackathon02**
- **Hệ điều hành (Windows/macOS):windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
Ls -Force -Recurse
mv .\quy_dinh_thue.txt .\docs\
mkdir backup
cp .\data\don_thue_thang_5.xlsx .\backup\
rm .\temp_505.tmp
cd .\logs\; ls; cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   7:49 AM                backup
d-----        11/11/2026   7:45 AM                data
d-----        11/11/2026   7:48 AM                docs
d-----        11/11/2026   7:35 AM                evidence
d-----        11/11/2026   7:38 AM                logs
d-----        11/11/2026   7:33 AM                web
------         11/3/2026   7:07 AM             72 .env
-a----         11/3/2026   7:07 AM           2409 bai_lam.md


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/11/2026   7:45 AM          11078 don_thue_thang_5.xlsx


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/11/2026   7:45 AM          11078 don_thue_thang_5.xlsx


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            159 quy_dinh_thue.txt


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            934 rental.log


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   7:33 AM                images
------         11/3/2026   7:07 AM            582 app.js
------         11/3/2026   7:07 AM            534 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3090 logo-campgo.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
sls "status=500" .\logs\rental.log

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
logs\rental.log:6:2026-05-28 08:17:12 POST /api/kho-do status=500
logs\rental.log:7:2026-05-28 08:20:23 POST /api/thue-do status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
sls "status=404" .\logs\rental.log | Measure-Object -Line

```

```text
Lines Words Characters Property
----- ----- ---------- --------
    4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-05-28 08:13:01 GET /combo-cu status=404
2026-05-28 08:30:56 GET /images/leu-6.jpg status=404
2026-05-28 08:33:07 GET /images/leu-6.jpg status=404
2026-05-28 08:49:24 GET /combo-cu status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Không hiển thị logo | GET file:///C:/Users/LeMinhHP/Downloads/starter-kit/starter-kit/thue-do-cam-trai-website/web/images/logo.png net::ERR_FILE_NOT_FOUND | sửa lại link trong VS Code |
| 2 | sai tên cấu trúc | app.js:18
 Uncaught ReferenceError: hienThiBangThue is not defined
(anonymous)	@	app.js:18
﻿ | Sửa lại tên cấu trúc |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- **Expected:** 
- **Actual:** 
- **Log:** 

### Câu tìm kiếm Google

```text
stackoverflow.com "Uncaught ReferenceError: hienThiBangThue is not defined"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_thue_thang_5.xlsx`, không cần ghi vào đây.
