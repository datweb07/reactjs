### 1. React JS là gì? Học React từ cơ bản đến nâng cao cho người mới

#### React là gì?
- **React** là thư viện JavaScript cho phần **giao diện người dùng (UI)**, do Facebook (hiện là Meta) phát triển và sử dụng trong các sản phẩm lớn như:
  - Facebook
  - Instagram
  - Netflix
  - Shopee
  - TikTok
- React có các đặc điểm nổi bật:
  - **Mã nguồn mở, miễn phí.**
  - Phát triển từ năm 2013 (11 năm tính đến thời điểm hiện tại).
  - Được sử dụng phổ biến bởi các công ty công nghệ lớn.
- React giúp phát triển frontend linh hoạt, hiệu quả, tập trung vào xây dựng các **component (thành phần)** giúp tái sử dụng mã nguồn.

#### Khái niệm Component trong React
- Một trang web thường có nhiều thành phần giống nhau (ví dụ: avatar, bài đăng, biểu tượng).
- React chia giao diện thành các **component** nhỏ, mỗi component chứa đầy đủ HTML, CSS, JavaScript.
- Việc tái sử dụng component giúp giảm thiểu công sức khi cập nhật giao diện.
- Ví dụ: Trên mạng xã hội như X (trước đây là Twitter), mỗi bài đăng là một component với:
  - Avatar
  - Tên người dùng
  - Thời gian đăng bài
  - Nội dung (văn bản, hình ảnh, video)
- Khi cập nhật nội dung bài đăng hoặc bình luận, chỉ component đó được cập nhật, không phải tải lại toàn bộ trang.

#### Cơ chế cập nhật giao diện của React: Virtual DOM
- React sử dụng **Virtual DOM (DOM ảo)** để tối ưu hiệu năng:
  
| Bước | Mô tả |
| :---: | :--- |
| 1 | Render lần đầu: Tạo một bản cứng Virtual DOM, hiển thị giao diện trên trình duyệt. |
| 2 | Khi có thay đổi: Tạo bản cập nhật Virtual DOM mới. |
| 3 | So sánh: Khảo sát giữa Virtual DOM mới và cũ để tìm ra sự khác biệt. |
| 4 | Cập nhật: Chỉ cập nhật các phần khác biệt lên DOM thật trên trình duyệt. |

- Virtual DOM nằm trong bộ nhớ, không hiển thị trực tiếp, giúp chỉ cập nhật những phần thay đổi thay vì tải lại toàn bộ trang.
- Ví dụ dùng Facebook: Khi có tin nhắn mới hay thông báo mới, chỉ component tương ứng được cập nhật mà không phải tải lại trang.

#### Lợi ích và xu hướng React
- React được đánh giá cao, đứng đầu thị trường frontend so với các framework phổ biến như Angular, Vue trong 90 ngày gần nhất (dữ liệu từ Google Trends).
- Việc học React đem lại cơ hội phát triển kỹ năng, cập nhật và tối ưu giao diện web theo chuẩn hiện đại.
- Video khuyến khích người học không bỏ qua bước học cơ bản mà nên tiến bộ từ từ, làm quen từng phần rồi thực hiện các dự án hoàn thiện.

---

### Bảng tổng hợp các khái niệm chính về React và Frontend

| Thuật ngữ | Định nghĩa |
| :--- | :--- |
| **Frontend** | Phần giao diện người dùng, hiển thị và tương tác trên trình duyệt (HTML, CSS, JavaScript). |
| **Backend** | Phụ trách xử lý logic, lưu trữ dữ liệu và phản hồi các yêu cầu từ frontend. |
| **React** | Thư viện JavaScript dùng để xây dựng UI, được phát triển bởi Meta, mã nguồn mở, miễn phí, có mức độ phổ biến lớn. |
| **Component** | Khối mã UI nhỏ bao gồm HTML, CSS, JS, có thể tái sử dụng và cập nhật độc lập trong React. |
| **Virtual DOM** | Bản sao DOM thật nằm trong bộ nhớ, dùng để so sánh và cập nhật hiệu quả các thay đổi trên giao diện. |

---

### Kết luận chính
- React giúp phát triển giao diện web một cách hiệu quả và linh hoạt thông qua việc xây dựng các component có khả năng tái sử dụng.
- Ứng dụng cơ chế Virtual DOM giúp cập nhật giao diện tối ưu, giảm tải đáng kể so với việc tải lại toàn bộ trang.
