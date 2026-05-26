#### 1. Tổng quan về hàm trong JavaScript
- Có **3 cách khai báo hàm chính**:
  - Function Declaration (khai báo hàm truyền thống)
  - Function Expression (gán hàm vào biến)
  - Arrow Function (hàm mũi tên, phần sau sẽ giới thiệu)
- Hàm là một khối mã thực thi nhiệm vụ xác định, có thể có tham số đầu vào và trả về kết quả.
- Hàm có thể gọi nhiều lần với các tham số khác nhau nhằm tái sử dụng mã nguồn.

#### 2. Function Declaration (khai báo hàm truyền thống)
- Cú pháp:
  

  **function name(parameters) {body}**


- Ví dụ khai báo hàm không tham số:

```javascript
  function xinChao() {
    console.log('Xin chào bạn');
  }

```

* Gọi hàm bằng tên, không có từ khóa `function`:
```javascript
xinChao();

```


* Hàm có tham số:
```javascript
function xinChao2(username) {
  console.log('Xin chào bạn ' + username);
}

```


* Có thể gọi nhiều lần với các tham số khác nhau để thấy tính tái sử dụng.
* Hàm có thể trả về giá trị bằng từ khóa `return`:
```javascript
function tich(a, b) {
  return a * b;
}
const kq = tich(4, 5); // Kết quả = 20

```


* Tham số có thể có giá trị mặc định:
```javascript
function xinChao3(username = 'no input name') {
  console.log('Xin chào bạn ' + username);
}
xinChao3();     // In ra: Xin chào bạn no input name
xinChao3('Lan'); // In ra: Xin chào bạn Lan

```


* Trường hợp truyền thiếu tham số cần chú ý, ví dụ như khi chỉ muốn truyền tham số thứ hai, cần truyền `undefined` ở tham số thứ nhất để giữ giá trị mặc định:
```javascript
function tich(c = 1, d = 9) {
  return c * d;
}
console.log(tich(undefined, 8)); // Kết quả 8

```

#### 3. Function Expression (gán hàm vào biến)

* Cú pháp:
**const bienTen = function(parameters) {body}**


* Khác với `Function Declaration` là hàm không có tên riêng mà được gán vào một biến.
* Ví dụ:
```javascript
const tong = function(a, b) {
  return a + b;
};
console.log(tong(5, 3)); // 8

```


* Gọi hàm qua biến, sử dụng tham số bình thường.
* Về cơ bản, hai cách này (Declaration và Expression) tương đương về hiệu quả, chỉ khác nhau ở cú pháp và cơ chế Hoisting.

### Bảng so sánh các kiểu khai báo hàm

| Đặc điểm | Function Declaration | Function Expression |
| --- | --- | --- |
| **Tên hàm** | Có tên riêng | Không có tên, gán vào biến |
| **Cú pháp** | `function name(params) {...}` | `const varName = function(params) {...}` |
| **Gọi hàm** | Chỉ cần dùng tên hàm | Gọi thông qua tên biến |
| **Hoisting (Nâng lên)** | Có (có thể gọi trước khi khai báo) | Không (phải khai báo trước khi gọi) |
| **Thường dùng** | Khai báo chính, rõ ràng | Khi muốn gán hàm cho biến, xử lý động |
