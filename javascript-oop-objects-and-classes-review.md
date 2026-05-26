### Các khái niệm chính

- **Object trong JavaScript:** - Object (đối tượng) là cấu trúc dữ liệu nhóm các giá trị theo cặp **key:value**.  
  - Khai báo object theo kiểu **Object Literal** bằng cách sử dụng cặp ngoặc nhọn `{}`.  
  - Thuộc tính (properties) là các cặp key:value, ví dụ:  
    - `name: "Lan"` (key là `name`, value là `"Lan"`).  
    - Các cặp key:value được phân tách nhau bởi dấu phẩy `,`.  
  - **Phương thức (methods)** là hàm được khai báo bên trong object, không cần dùng từ khóa `function` mà chỉ ghi trực tiếp tên hàm, ví dụ:
    ```javascript
    xinChao() {
      console.log("Xin chào bạn");
    }
    ```

- **Truy cập thuộc tính và phương thức của Object:** - Hai cách truy cập chính:  
    - **Dot notation (Dấu chấm):** `user.name`, `user.tuoi`  
    - **Bracket notation (Ngoặc vuông):** `user["giới tính"]` (dùng khi key có dấu cách hoặc ký tự đặc biệt).  
  - Lưu ý: Các thuộc tính nên đặt tên theo quy tắc định danh để ưu tiên dùng dot notation cho dễ đọc, tránh viết key có chứa dấu cách.

- **Kết quả gọi phương thức trong Object:** - Nếu phương thức không có từ khóa `return` trả về giá trị, kết quả nhận được mặc định sẽ là **`undefined`**.  
  - Phương thức có thể `return` một giá trị cụ thể, ví dụ: `return 1;`.

### Giới thiệu về Class trong JavaScript

- Khi cần tạo nhiều đối tượng giống nhau (ví dụ: nhiều sinh viên với cùng các thuộc tính như tên, tuổi, quê quán...), chúng ta **không thể khai báo từng đối tượng một cách thủ công**, vì rất mất thời gian và gây lặp mã nguồn.  
- **Class** (lớp) là khuôn mẫu dùng để định nghĩa và sinh ra các đối tượng (instances) có cùng cấu trúc thuộc tính và hành vi.  
- Cách khai báo một Class:  
```javascript
  class User {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    xinChao() {
      console.log("Xin chào bạn");
      return 1;
    }
  }

```

* `constructor` là hàm khởi tạo, nhận các tham số đầu vào để thiết lập giá trị ban đầu cho các thuộc tính của đối tượng.
* Bên trong `constructor`, từ khóa `this` đại diện cho chính thực thể (đối tượng) đang được khởi tạo.
* Tạo đối tượng từ Class:
```javascript
const user1 = new User("Nam", 60);
const user2 = new User("Trung", 70);

```

* Mỗi đối tượng đều có thuộc tính và phương thức riêng biệt được khởi tạo dựa trên khuôn mẫu Class chung.
* Có thể truy cập thuộc tính bằng cú pháp: `user1.name`, hoặc gọi phương thức: `user2.xinChao()`.

### Bảng so sánh Object Literal và Class

| Tiêu chí | Object Literal | Class |
| --- | --- | --- |
| **Khai báo** | Trực tiếp bằng cặp ngoặc nhọn `{}`. | Sử dụng từ khóa `class`. |
| **Khả năng tái sử dụng** | Khó áp dụng khi có nhiều đối tượng tương tự. | Tạo ra khuôn mẫu chuẩn để dễ dàng sinh nhiều đối tượng. |
| **Tạo đối tượng mới** | Mỗi đối tượng phải được khai báo riêng lẻ. | Sử dụng từ khóa `new` để tạo thực thể từ Class. |
| **Thuộc tính và phương thức** | Khai báo trực tiếp bên trong từng đối tượng. | Định nghĩa tập trung trong Class thông qua `constructor` và method. |
| **Tính linh hoạt** | Thích hợp cho số lượng ít đối tượng cấu trúc đơn giản. | Phù hợp cho số lượng lớn đối tượng và có khả năng mở rộng hệ thống tốt hơn. |

### Các điểm nhấn quan trọng

* **Object Literal** chỉ phù hợp với các trường hợp khai báo một vài đối tượng riêng lẻ, không tối ưu khi hệ thống cần quản lý nhiều đối tượng cùng loại.
* **Class** giúp tái sử dụng mã nguồn và dễ dàng tạo ra nhiều đối tượng có cùng cấu trúc, giảm thiểu tối đa việc trùng lặp code.
* Kỹ thuật truy cập thuộc tính và phương thức của thực thể tạo từ Class hoàn toàn tương tự như Object nhưng mang tính tường minh, có khuôn mẫu rõ ràng hơn.
* Việc dùng **dot notation** luôn được ưu tiên khi tên key hợp lệ; khi key có dấu cách hoặc chứa ký tự đặc biệt thì bắt buộc phải dùng **bracket notation**.
* Hàm trong Object hoặc Class có thể trả về giá trị hoặc không; nếu không sử dụng từ khóa return để chỉ định, hàm sẽ mặc định trả về **`undefined`**.

### Kết luận chính

* **Hiểu và sử dụng Object Literal giúp quản lý các nhóm dữ liệu có liên quan đến nhau một cách đơn giản và nhanh chóng.** 
- **Class là công cụ mạnh mẽ để tạo hàng loạt đối tượng cùng mẫu, giúp tổ chức cấu trúc và tái sử dụng mã nguồn hiệu quả trong lập trình hướng đối tượng (OOP).** 
- Việc áp dụng nhuần nhuyễn tư duy hướng đối tượng là nền tảng cốt lõi trước khi tiếp cận các thư viện và framework hiện đại như ReactJS.
