# 🔐 Ứng Dụng Truyền File Có Ký Số

Ứng dụng web cho phép người dùng **upload file**, **tạo chữ ký số**, và **xác minh tính toàn vẹn** của file đã ký. Đây là công cụ lý tưởng cho các tình huống cần **bảo mật**, **chứng thực**, và **chia sẻ an toàn** tệp tin giữa các bên.

---

## 🌐 Tính Năng Chính

### 1. 📤 Upload & Ký Số File
- Cho phép người dùng chọn hoặc kéo thả file.
- Hệ thống tự động tạo mã băm (hash) và ký số file.
- Hiển thị thông tin: tên file, kích thước, thời gian upload, mã hash và chữ ký số.
- Có thể tải về file gốc hoặc gói zip chứa cả file và chữ ký số.

### 2. ✅ Xác Minh Chữ Ký Số
- Người dùng chọn file bất kỳ và nhập chữ ký số để kiểm tra.
- Hệ thống kiểm tra tính hợp lệ bằng cách so sánh mã hash và chữ ký.
- Thông báo kết quả: hợp lệ hoặc không hợp lệ.

### 3. 📁 Danh Sách File
- Xem toàn bộ file đã upload lên hệ thống.
- Tải về từng file hoặc toàn bộ gói chữ ký.
- Thông tin hiển thị gồm tên file, dung lượng, thời gian và mã hash.

---

## 🖼️ Giao Diện Người Dùng

- **Thiết kế hiện đại, trực quan và thân thiện.**
- Hệ thống tab giúp chuyển đổi nhanh giữa các chức năng.
- Hỗ trợ hiệu ứng kéo-thả file và hiệu ứng ✨ sinh động.
- Giao diện responsive, hiển thị tốt trên cả máy tính và thiết bị di động.

---

## ⚙️ Yêu Cầu Backend

Mặc dù giao diện là thuần HTML/CSS/JS, để hoạt động đầy đủ bạn cần một server backend để xử lý các tác vụ:

### Các API cần thiết:
| Phương thức | Endpoint | Mô tả |
|------------|----------|-------|
| `POST` | `/upload` | Nhận file, ký số, trả về thông tin file và chữ ký. |
| `POST` | `/verify` | Nhận file + chữ ký số, xác minh tính hợp lệ. |
| `GET` | `/list_files` | Trả về danh sách file đã upload. |
| `GET` | `/download/:id` | Tải xuống file gốc. |
| `GET` | `/download_package/:id` | Tải xuống file + chữ ký dưới dạng gói. |

> Gợi ý backend nên dùng: `Flask`, `ExpressJS`, `FastAPI`, v.v.

---

## 🛠 Cài Đặt & Triển Khai

1. **Clone dự án frontend**
   ```bash
   git clone https://github.com/ten-repo/kyso-file-transfer.git
   cd kyso-file-transfer
