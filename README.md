# 📈 Quản Lý Danh Mục Đầu Tư Tài Sản Số
> **Hệ thống quản lý quỹ mô phỏng (Simulated Fund Management System)**

![Logo Dự Án](logo.jpg)

**Nhóm phát triển:** Nhóm 2_48K33

## 📖 Giới thiệu

Đây là ứng dụng web đơn trang (Single-page Application) giúp các nhóm quản lý quỹ đầu tư tài sản số (Crypto/RWA) một cách tập trung và hiệu quả. Ứng dụng được thiết kế cho mục đích học tập/mô phỏng, cho phép theo dõi NAV (Net Asset Value), quản lý danh mục, ghi nhật ký giao dịch và xuất báo cáo tự động.

Hệ thống sử dụng cơ chế **Không gian làm việc (Workspace)** dựa trên `Team ID`, cho phép các thành viên trong cùng một nhóm truy cập và cập nhật dữ liệu chung theo thời gian thực.

## ✨ Tính năng nổi bật

### 1. 🏢 Quản lý Không gian làm việc (Workspace)
- Đăng nhập ẩn danh an toàn.
- Tạo hoặc tham gia không gian làm việc chung bằng **Tên Nhóm (Team ID)**.
- Dữ liệu đồng bộ hóa thời gian thực giữa các thành viên.

### 2. 📊 Quản lý Danh mục & NAV (Portfolio Tracking)
- **Cập nhật giá tự động:** Tích hợp API CoinGecko để lấy giá token theo thời gian thực (VND).
- **Tính toán NAV:** Tự động tính Tổng tài sản ròng dựa trên danh mục và nợ/phí.
- **Biểu đồ trực quan:** - Biểu đồ tròn (Pie Chart) phân bổ tài sản.
  - Biểu đồ đường (Line Chart) theo dõi lịch sử tăng trưởng NAV.
- **Snapshot:** Lưu lại trạng thái NAV tại các thời điểm chốt sổ.

### 3. 📝 Nhật ký Giao dịch (Transaction Log)
- Ghi lại mọi hoạt động: Mua, Bán, Staking, Unstake, Nạp/Rút tiền.
- **Auto-Update:** Tùy chọn tự động cập nhật số dư trong danh mục đầu tư khi nhập giao dịch mới.
- Tính năng chỉnh sửa/xóa giao dịch đã nhập.

### 4. ⚠️ Quản trị Rủi ro (Risk Management)
- Ghi nhận các kịch bản rủi ro giả định (Token giảm giá, De-peg...).
- Lưu trữ giải pháp và phản ứng của nhóm quản lý quỹ.

### 5. 📂 Hồ sơ & Báo cáo
- Lưu trữ nội dung văn bản cho Hợp đồng quỹ, Chiến lược, Phân tích.
- **Xuất Excel (Export):** Tính năng mạnh mẽ giúp xuất toàn bộ dữ liệu (Thiết kế quỹ, Danh mục, Lịch sử NAV, Giao dịch) ra file Excel `.xlsx` chuyên nghiệp.

## 🛠 Công nghệ sử dụng

Ứng dụng được xây dựng theo kiến trúc **Serverless** và **Buildless** (chạy trực tiếp không cần build):

* **Frontend:** HTML5, JavaScript (ES6 Modules).
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) (qua CDN).
* **Database & Auth:** [Google Firebase](https://firebase.google.com/) (Firestore & Authentication).
* **Biểu đồ:** [Chart.js](https://www.chartjs.org/).
* **Xử lý Excel:** [SheetJS (XLSX)](https://sheetjs.com/).
* **Icons:** [Lucide Icons](https://lucide.dev/).
* **Price Data:** CoinGecko API.

## 🚀 Hướng dẫn cài đặt và sử dụng

Vì đây là file HTML tích hợp sẵn, bạn không cần cài đặt Node.js hay server phức tạp.

### Cách 1: Chạy trực tiếp
1.  Tải file `index.html` và `logo.jpg` về cùng một thư mục.
2.  Mở file `index.html` bằng trình duyệt web hiện đại (Khuyên dùng: **Google Chrome**, **Microsoft Edge**).
3.  Nhập tên nhóm (Ví dụ: `Nhom2-Test`) và bắt đầu sử dụng.

### Cách 2: Sử dụng Live Server (Khuyên dùng)
Để tránh các lỗi liên quan đến CORS khi tải module ES6 từ CDN:
1.  Cài đặt Extension **Live Server** trên VS Code.
2.  Chuột phải vào file `index.html` -> Chọn **"Open with Live Server"**.

## 📖 Hướng dẫn sử dụng chi tiết

1.  **Bước 1: Đăng nhập nhóm**
    * Nhập tên nhóm (VD: `QuyDauTu-Nhom2`). Nhấn nút "Tải/Tạo Không gian làm việc".
2.  **Bước 2: Thiết kế quỹ (Tab 1)**
    * Nhập các thông tin cơ bản: Tên quỹ, Chiến lược, Thành viên. Hệ thống tự động lưu khi bạn nhập.
3.  **Bước 3: Nhập số dư đầu kỳ (Tab 3 hoặc Tab 2)**
    * Vào Tab 3 (Giao dịch) để nhập các lệnh "Nạp tiền" (Deposit) hoặc "Mua" (Buy). Tích chọn "Tự động cập nhật" để hệ thống tính vào Tab 2.
4.  **Bước 4: Theo dõi NAV (Tab 2)**
    * Xem biểu đồ phân bổ.
    * Cuối mỗi ngày, nhập chi phí (nếu có) và nhấn **"Lưu Snapshot NAV"** để vẽ biểu đồ tăng trưởng.
5.  **Bước 5: Xuất báo cáo**
    * Nhấn nút màu xanh lá **"Xuất Báo cáo Excel"** ở góc trên bên phải để tải file báo cáo đầy đủ về máy.

## ⚠️ Lưu ý quan trọng
* **Dữ liệu:** Dữ liệu được lưu trên Firebase Cloud. Hãy nhớ chính xác **Tên Nhóm (Team ID)** của bạn để truy cập lại dữ liệu lần sau.
* **API CoinGecko:** Phiên bản miễn phí của CoinGecko có giới hạn số lần gọi. Nếu giá không hiện, hãy đợi khoảng 1 phút và tải lại trang.

---
© 2025 Được phát triển bởi **Nhóm 2_48K33**.
