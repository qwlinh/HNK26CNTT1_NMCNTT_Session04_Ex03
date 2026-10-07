# Phần 1: Mã nguồn



## 1. Tạo cây thư mục dự án Farm-Manager gồm các phân vùng code\app, database\db, và logs\guides
[ New-Item -ItemType Directory -Path ".\Farm-Manager\code\app", ".\Farm-Manager\database\db", ".\Farm-Manager\logs\guides" -Force ]


 - Ý nghĩa lệnh: Tạo mới thư mục trên hệ thống.

 - Tham số -Force: Ép buộc tạo thư mục, tự động tạo các cấp thư mục cha/con lồng nhau đệ quy nếu chưa tồn tại mà không báo lỗi xung đột.


## 2. Tạo 3 file rỗng bên trong thư mục app (main.py, models.py, utils.py)
[ New-Item -ItemType File -Path ".\Farm-Manager\code\app\main.py", ".\Farm-Manager\code\app\models.py", ".\Farm-Manager\code\app\utils.py" -Force ]

 
 - Ý nghĩa lệnh: Tạo các file mã nguồn Python trắng phục vụ ứng dụng.

 - Tham số -Force: Ghi đè file nếu file đó đã tồn tại sẵn trong thư mục, giúp script chạy liền mạch không bị ngắt quãng.


## 3. Sao chép toàn bộ thư mục logs sang bản lưu trữ logs-backup
[ Copy-Item -Path ".\Farm-Manager\logs" -Destination ".\Farm-Manager\logs-backup" -Recurse -Force ]

 - Ý nghĩa lệnh: Sao chép thư mục từ nguồn sang đích.

 - Tham số -Recurse: Bắt buộc phải có để sao chép đệ quy toàn bộ thư mục con (guides) và các file bên trong, tránh việc chỉ tạo ra một thư mục rỗng.

 - Tham số -Force: Cho phép ghi đè tự động nếu thư mục đích logs-backup đã tồn tại từ trước.

# Phần 2: Kiểm thử
## 1. Lệnh liệt kê cây thư mục sau khi chạy
Sau khi thực thi xong các câu lệnh trên, bạn gõ lệnh sau để kiểm tra cấu trúc:


[ ls .\Farm-Manager hoặc: dir .\Farm-Manager ]
## 2. Giải thích: Tại sao cần dùng đường dẫn tương đối (.\) thay vì đường dẫn tuyệt đối (C:\...)?
 - Tính di động cao: Đường dẫn tương đối với tiền tố .\ giúp câu lệnh hoạt động chính xác ở bất kỳ vị trí hay thư mục nào mà bạn đang mở terminal (Desktop, Documents, hoặc ổ đĩa khác).

 - Tránh lỗi gắn cứng (Hard-code): Nếu dùng đường dẫn tuyệt đối sẽ bị lỗi ngay lập tức khi chạy trên một máy tính khác hoặc phân vùng khác. Sử dụng .\ giúp mã nguồn chuyên nghiệp, linh hoạt và dễ dàng triển khai từ xa..
