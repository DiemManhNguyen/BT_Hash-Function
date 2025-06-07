



## 🏷 Hệ Thống Đăng Nhập & Truyền File Giữa Người Dùng
Trang web **"Hệ Thống Đăng Nhập & Truyền File Giữa Người Dùng"** là một ứng dụng hỗ trợ người dùng đăng nhập và chia sẻ tệp tin một cách dễ dàng, an toàn. Sau khi đăng nhập thành công, người dùng có thể chọn người nhận từ danh sách tài khoản khác, tải lên tệp từ thiết bị của mình và gửi đến người nhận đã chọn. Hệ thống hiển thị danh sách các tệp đã gửi hoặc nhận kèm theo thông tin chi tiết như người gửi, người nhận, và mã SHA-256 để xác minh tính toàn vẹn của tệp. Giao diện được thiết kế thân thiện, hiện đại, hỗ trợ thao tác trực quan và dễ sử dụng. Trang web kết nối với backend thông qua các API như `/login`, `/upload`, `/list_users`, `/list_files`, và `/download`, giúp quản lý người dùng và tệp một cách hiệu quả.
## 📄 Mô tả chi tiết ngắn gọn về hoạt động của trang web:
Người dùng có thể chọn người nhận từ danh sách tài khoản khác.

-Tải tệp từ máy tính và gửi đến người nhận đã chọn.

-Tệp được gửi sẽ được hiển thị trong danh sách, bao gồm thông tin người gửi, người nhận và mã băm SHA-256 để xác minh tính toàn vẹn.

-Người dùng có thể tải về các tệp mình đã gửi hoặc nhận.

-Giao diện cho phép đăng xuất để chuyển về màn hình đăng nhập.
## 🎨 Giao Diện Của Trang Web
## 👤 Đăng nhập

## ➡️ Trang chính


## 💡 Chức năng chính của trang:
1. Đăng nhập người dùng

2. Tải lên và gửi file cho người khác

3. Xem danh sách file đã gửi/nhận

4. Tải file đã truyền về

5. Đăng xuất


## 📁 Cấu Trúc Thư Mục Của Dự Án
1. __pycache__/
Thư mục này được Python tự động tạo ra khi chạy chương trình.

Nó chứa các file bytecode đã biên dịch để chương trình chạy nhanh hơn lần sau.

🧱 File bên trong:

server.cpython-312.pyc: phiên bản biên dịch của server.py, được tạo khi chạy bằng Python 3.12.

2. uploads/
Đây là thư mục chứa các tệp tin mà người dùng đã tải lên thông qua trang web.

📄 File bên trong:

Data.txt: tệp văn bản người dùng có thể đã tải lên.

3. Hash_Function.html
Trang HTML giao diện chính của web.

Form đăng nhập

Giao diện chọn file và truyền file

Các script JavaScript và CSS được nhúng để tương tác và hiển thị đẹp mắt.

4. server.py
File Python xử lý phần backend của hệ thống.

Xử lý đăng nhập người dùng

Nhận và lưu trữ file upload vào thư mục uploads/

Tính toán mã băm SHA-256 cho các tệp

Trả về thông tin và danh sách file đã upload

## 🧾 Hướng dẫn sử dụng
✅ 1. Đăng nhập
Giao diện khởi đầu hiển thị form:

-Nhập tên đăng nhập

-Nhập mật khẩu

-Bấm nút "Đăng Nhập"

-Nếu đúng, giao diện chuyển sang phần truyền file.

-Nếu sai, hiển thị thông báo lỗi "Sai tài khoản hoặc mật khẩu!".

📤 2. Truyền file
Sau khi đăng nhập, hiện giao diện:

-Chọn người nhận từ danh sách.

-Chọn file từ máy tính bằng ô chọn tệp.

-Nhấn nút "Upload"

-Kết quả hiện ra:

-Tên file, mã băm SHA-256, người gửi và người nhận.

-Nút Tải về nếu cần tải lại file đó.

📄 3. Danh sách file
Phía dưới có phần Danh sách file:

-Hiện tất cả các file mà bạn là người gửi hoặc nhận.

-Hiển thị rõ tên file, người gửi, người nhận, mã SHA-256.

-Có nút Tải về tương ứng từng file.

🔄 4. Đăng xuất
-Nhấn nút "Quay lại đăng nhập" để đăng xuất và quay về form đăng nhập.
## ✅Cách chạy ứng dụng:
🔧 Bước 1: Cài đặt môi trường Python
Đảm bảo bạn có Python (>=3.6). Kiểm tra:

Tạo môi trường ảo (tùy chọn):

Cài các thư viện cần thiết:

## 🚀 Bước 2: Chạy server Flask
Đặt file server.py vào thư mục gốc dự án.

Chạy lệnh sau:

Flask sẽ chạy ở địa chỉ mặc định:

## 🌐 Bước 3: Mở giao diện người dùng
Mở index.html bằng trình duyệt:

Cách 1: Click đúp vào file Hash_Function để mở bằng trình duyệt (hoạt động tốt nếu server cho phép localhost CORS).

Cách 2: Dùng extension như "Live Server" (trên VS Code) để chạy HTML trên địa chỉ ví dụ: http://127.0.0.1:5500/Hash_Function.

## ✅ Luồng hoạt động của ứng dụng
▶️ Giao diện chính (Hash_Function) cho phép:
Đăng nhập với các tài khoản có sẵn:

Gửi file: chọn file, chọn người gửi và người nhận ⇒ gửi lên /upload.

Xem danh sách file đã gửi, gồm: tên file, mã SHA256, người gửi, người nhận.

Tải file từ server với đường dẫn /download/<filename>.

## 🧪 Kiểm thử nhanh
Đăng nhập thử với:

Upload file bất kỳ và kiểm tra trên server:

File sẽ được lưu vào thư mục uploads/.

Danh sách sẽ được cập nhật trong endpoint /list_files.

## PHÍA TRÊN LÀ NHỮNG PHẦN GIỚI THIỆU CÁC DÙNG SỬ DỤNG VÀ HOẠT ĐỘNG VÀ NHIỀU PHẦN KHÁC NỮA VỀ TRANG WEB Hash_Function CỦA TÔI: BẠN CÓ THỂ DONWLOAD BÀI CỦA TÔI VỀ BẰNG GITBASH VỚI LỆNH SAU: GIT CLONE <LINK BÀI DỰ ÁN CỦA TÔI> CHÚC BẠN CÓ TRẢI NGHIỆM TỐT VỀ DỰ ÁN CỦA TÔI
