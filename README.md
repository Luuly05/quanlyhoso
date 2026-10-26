# Ocean Deadline Tracker

Ứng dụng Quản lý Hạn Hồ sơ CSKH & Cảnh báo Khóa Tên miền.

---

## 🛠 Hướng dẫn kết nối Cơ sở dữ liệu PostgreSQL Nội bộ

### Bước 1: Cấu hình file `.env`
Mở file `.env` tại thư mục gốc của dự án và điền thông tin máy chủ PostgreSQL nội bộ:
```env
# Địa chỉ IP hoặc tên miền máy chủ nội bộ (ví dụ: 192.168.1.100 hoặc localhost)
DB_HOST=127.0.0.1
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password_here
DB_NAME=ocean_tracker
DB_SSL=false

# Cổng Backend API
PORT=5000
```

### Bước 2: Tự động khởi tạo bảng và dữ liệu mẫu
Chạy lệnh sau để tạo các bảng (`orders`, `document_checklists`, `contact_logs`, `deadline_alerts`) và nạp dữ liệu mẫu ban đầu:
```bash
npm run db:init
```

### Bước 3: Khởi động hệ thống
Bạn có thể chạy cả Frontend và Backend cùng lúc:
```bash
npm run dev:all
```
Hoặc mở 2 cửa sổ terminal riêng biệt:
- **Terminal 1 (Backend API):** `npm run server` (chạy trên cổng `5000`)
- **Terminal 2 (Frontend React):** `npm run dev` (chạy trên cổng `3000`)

---

## 🐳 Hướng dẫn chạy Docker
```bash
docker build -t ocean-deadline-tracker .
docker run -p 3000:80 ocean-deadline-tracker
```
Mở trình duyệt truy cập: `http://localhost:3000`
