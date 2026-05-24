- **Phương pháp 1: Tạo dự án React với CodeSandbox**
  - Truy cập trang web tạo dự án React bằng cách nhập từ khóa `react.new` trên thanh địa chỉ trình duyệt.
  - Hệ thống tự động chuyển hướng đến CodeSandbox và tạo dự án React ban đầu có file `App.js`.
  - Phải đăng nhập (Google, Apple, GitHub) mới có thể chỉnh sửa mã nguồn.
  - Code thay đổi được hiển thị trực tiếp trên tab xem kết quả (preview).

- **Phương pháp 2: Tạo và quản lý dự án React trên VS Code**
  - Yêu cầu cài đặt sẵn **VS Code**.
  - Cài đặt tiện ích mở rộng **ESLint** nhằm kiểm tra lỗi cú pháp và mã ngay khi soạn thảo hoặc khi lưu file.
    - Có thể cấu hình ESLint chạy kiểm tra “onsave” (khi lưu) hoặc “ontime” (ngay khi gõ).
  - Cài đặt **Node.js version 2.12.0** (hoặc phiên bản tương thích với khóa học) để đảm bảo không phát sinh lỗi do khác biệt phiên bản.
    - Khuyên dùng bản LTS (Long Term Support) để hỗ trợ lâu dài và ổn định.
  - Tạo thư mục dự án trên ổ đĩa, mở folder này bằng VS Code.
  - Sử dụng terminal trong VS Code, chạy các câu lệnh:
    1. `npm create vite@latest`
    2. Chọn tên dự án, framework (React) và ngôn ngữ (JavaScript).
    3. Di chuyển vào thư mục dự án với câu lệnh cd {tên_project} 
    4. Cài đặt các gói cần thiết bằng npm install
    5. Chạy ứng dụng với npm run dev
  - Khi chạy thành công, VS Code cung cấp đường link truy cập web ứng dụng.
  - Lưu ý quan trọng về vị trí working directory: Cần phải chắc chắn đang ở thư mục dự án mới chạy lệnh `npm run dev`.
  - Mẹo: mở trực tiếp folder dự án trong VS Code để khi mở terminal con trỏ đã đứng đúng thư mục, tránh lỗi chạy lệnh sai vị trí.

### Bảng so sánh hai phương pháp tạo dự án React

| Tiêu chí                   | CodeSandbox                              | VS Code + Node.js                    |
|----------------------------|----------------------------------------|------------------------------------|
| Cài đặt                    | Không cần (online)                      | Cần cài VS Code, Node.js, ESLint   |
| Môi trường làm việc         | Trình duyệt                            | Máy cá nhân (offline)               |
| Đăng nhập                  | Cần đăng nhập tài khoản (Google, GitHub, Apple) | Không cần                            |
| Chỉnh sửa                  | Trực tuyến, thay đổi tự động            | Soạn thảo trong VS Code             |
| Hỗ trợ kiểm lỗi              | *Not specified*                        | ESLint kiểm lỗi cú pháp            |
| Quản lý phiên bản           | Không rõ                             | Cần chọn Node.js đúng phiên bản phù hợp |
| Khả năng mở rộng và tùy chỉnh| Giới hạn                            | Toàn quyền tùy chỉnh, cài thêm thư viện |
| Chạy ứng dụng               | Trực tiếp trên web                     | Phải chạy lệnh `npm run dev`       |
