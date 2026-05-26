### So sánh tổng quan Arrow Function và Function Expression

| Đặc điểm | Function Expression | Arrow Function |
| :--- | :--- | :--- |
| **Cách khai báo** | Dùng từ khóa `function`. | Không dùng từ khóa `function`, thay bằng mũi tên `=>` ("arrow"). |
| **Cách đặt tên** | Đặt tên thông qua biến được gán. | Đặt tên thông qua biến được gán. |
| **Tham số (Parameters)** | Truyền trong dấu ngoặc đơn `()`. | Truyền trong dấu ngoặc đơn `()`. |
| **Thân hàm** | Luôn có dấu ngoặc nhọn `{}`, cần từ khóa `return` nếu muốn trả về giá trị. | Có thể bỏ dấu ngoặc nhọn và từ khóa `return` nếu chỉ có một biểu thức đơn giản (implicit return). |
| **Cú pháp ngắn gọn** | Dài dòng hơn. | Ngắn gọn và tường minh hơn. |

**Lưu ý:** Arrow Function còn được gọi là **Anonymous Function** (hàm ẩn danh), vì bản thân nó không có tên hàm cố định mà thường được định nghĩa trực tiếp hoặc gán vào một biến.

### Cấu trúc cơ bản của Arrow Function và ví dụ minh họa

**Mẫu cú pháp:**

$$
\text{const} \; \text{functionName} = (\text{parameter1}, \text{parameter2}) => \{ \text{body} \}
$$

- Ví dụ tính tích và tổng của hai số rồi cộng lại với nhau:

```javascript
const multiplyAndAdd = (a, b) => {
  const product = a * b;
  const sum = a + b;
  return product + sum;
};

```

* Kết quả khi gọi hàm `multiplyAndAdd(4, 5)` trả về:

$$4 \times 5 = 20; \quad 4 + 5 = 9; \quad 20 + 9 = 29$$

* Nếu hàm chỉ trả về một biểu thức đơn giản, có thể viết ngắn gọn như sau (implicit return):

```javascript
const multiply = (a, b) => a * b; // Tự động trả về kết quả của biểu thức

```

### Trả về đối tượng từ Arrow Function

* Khi Arrow Function trả về một đối tượng (Object literal), bạn phải **bọc đối tượng đó trong dấu ngoặc đơn** `()` để tránh gây lỗi cú pháp, do dấu ngoặc nhọn `{}` của đối tượng dễ bị trình biên dịch hiểu nhầm là phần thân hàm.

Ví dụ khai báo hàm trả về một đối tượng:

```javascript
const person = (name, age) => ({
  họ_tên: name,
  tuổi: age
});

```

* Gọi hàm `person('Lan', 70)` sẽ trả về đối tượng:

| Key | Value |
| --- | --- |
| **họ_tên** | 'Lan' |
| **tuổi** | 70 |

### Tổng hợp các điểm quan trọng

* **Arrow Function không cần từ khóa `function`**, thay vào đó sử dụng ký tự mũi tên `=>`.
* **Có thể bỏ qua từ khóa `return` và dấu ngoặc nhọn** nếu thân hàm chỉ có một câu lệnh trả về một biểu thức.
* **Khi trả về một đối tượng (Object)** theo cách viết ngắn gọn, bắt buộc phải bọc object đó trong dấu ngoặc đơn `()`.
* **Arrow Function được sử dụng phổ biến trong React** nhờ cú pháp ngắn gọn, dễ đọc và cơ chế tự động ràng buộc (bind) ngữ cảnh `this`.
* Nên đặt tên biến/hàm có ý nghĩa rõ ràng để người khác dễ dàng đọc hiểu chức năng.
* Cần hiểu rõ cả hai cách viết (có dấu ngoặc nhọn kèm `return` và không có dấu ngoặc nhọn) để thích ứng tốt khi đọc mã nguồn của các dự án khác nhau.

### FAQ (Câu hỏi thường gặp)

* **Arrow Function có thể không cần từ khóa `return` không?** Có, khi thân hàm chỉ chứa một biểu thức đơn, bạn có thể bỏ dấu ngoặc nhọn và từ khóa `return` để hàm tự động trả về giá trị của biểu thức đó.
* **Làm thế nào để trả về một đối tượng một cách ngắn gọn trong Arrow Function?** Bạn cần bọc đối tượng đó trong cặp dấu ngoặc đơn `()` ngay sau mũi tên `=>`, ví dụ: `() => ({ key: value })`.
* **Arrow Function khác Function Expression ở điểm nào?** Khác biệt lớn nhất nằm ở cú pháp ngắn gọn (không dùng từ khóa `function`), khả năng tự động return mà không cần dấu ngoặc nhọn, và đặc biệt là cách xử lý ngữ cảnh của từ khóa `this` (lexical scope).
* **Có thể đặt tên cho Arrow Function không?** Bản thân Arrow Function là hàm ẩn danh, nhưng bạn hoàn toàn có thể đặt tên cho nó bằng cách gán nó vào một hằng số hoặc một biến (ví dụ: `const myFunc = () => {}`).
* **Arrow Function thường được ứng dụng phổ biến ở đâu?** Được sử dụng rộng rãi trong các dự án React, các framework JavaScript hiện đại, và khi xử lý các phương thức của mảng như `map()`, `filter()`, `reduce()`.
