### Nội dung chính

#### 1. Khái niệm và cách khai báo mảng
- **Mảng là một dạng đặc biệt của Object** dùng để lưu trữ các giá trị theo thứ tự, với **chỉ số (Index) bắt đầu từ $0$**.
- Có hai cách khai báo mảng:
  - **Sử dụng dấu ngoặc vuông $[ \ ]$**: Cách phổ biến và đơn giản nhất.
  - **Sử dụng constructor `Array()`**: Giống với kiến thức trong ngôn ngữ C cơ bản, *không tập trung trong video này*.

- Ví dụ khai báo mảng:
  
  $$\text{const fruits} = ['cam', 'xoài', 'nho', 'táo'];$$

- Mảng trong JavaScript có tính động và có thể chứa nhiều kiểu dữ liệu khác nhau như **số, chuỗi, boolean, null, undefined, và cả mảng lồng nhau**.

#### 2. Truy cập phần tử trong mảng
- Truy cập phần tử dựa trên chỉ số index:
  - Ví dụ, để lấy phần tử đầu tiên: $$\text{fruits}[0] = 'cam'$$
  - Truy cập phần tử trong mảng lồng nhau:
    - Ví dụ mảng:  
      $$\text{const array} = [1, "Hello", true, null, undefined, [1, 2, 3]];$$
    - Lấy phần tử đầu tiên trong mảng con (nested array):
      $$\text{array}[5][0] = 1$$

#### 3. Phương thức thường dùng với mảng

##### 3.1 `push`
- Thêm một hoặc nhiều phần tử vào cuối mảng gốc.
- Ví dụ:
  $$\text{fruits.push('dứa')}$$
  Kết quả mảng sau khi thêm: `['cam', 'xoài', 'nho', 'táo', 'dứa']`.

##### 3.2 `map`
- Duyệt qua từng phần tử của mảng và tạo ra một mảng mới dựa trên kết quả của phép biến đổi trong hàm callback.
- Ví dụ nhân đôi giá trị các phần tử của mảng số:
  $$\text{const nums = [1, 2, 3, 4, 5];}$$
  $$\text{const nums2 = nums.map(item => item * 2);}$$
  Mảng kết quả mới: `[2, 4, 6, 8, 10]`.

- Biến đổi mảng giá trị sang mảng đối tượng (Object):
  $$\text{const objects = nums.map(item => ({ key: item }));}$$
  Mảng kết quả chứa các Object có khóa `key` và giá trị tương ứng.

##### 3.3 `findIndex`
- Tìm vị trí index của phần tử đầu tiên trong mảng thỏa mãn điều kiện kiểm tra.
- Ví dụ:
  $$\text{const index = fruits.findIndex(item => item === 'cam');}$$
  - Nếu tìm thấy phần tử phần tử phù hợp, hàm trả về chỉ số index đầu tiên của phần tử đó (ví dụ: $0$).
  - Nếu không có phần tử nào thỏa mãn điều kiện, hàm trả về $-1$.
- Lưu ý: Nếu có nhiều phần tử giống nhau cùng thỏa mãn điều kiện, phương thức chỉ trả về vị trí của phần tử đầu tiên tìm thấy.

### Kiến thức quan trọng

| Khái niệm | Mô tả |
| :--- | :--- |
| **Mảng (Array)** | Đối tượng đặc biệt, lưu trữ tập hợp dữ liệu có thứ tự với chỉ số index bắt đầu từ $0$. |
| **Khai báo mảng** | Sử dụng cú pháp dấu ngoặc vuông $[ \ ]$ hoặc hàm khởi tạo `Array()`. |
| **Kiểu dữ liệu trong mảng** | Đa dạng và linh hoạt: Số, chuỗi, boolean, null, undefined, mảng lồng nhau, object... |
| **Truy cập phần tử** | Sử dụng cú pháp `array[index]`, với index là số nguyên không âm bắt đầu từ $0$. |
| **`push`** | Phương thức dùng để thêm phần tử trực tiếp vào cuối mảng. |
| **`map`** | Phương thức tạo ra mảng mới từ mảng cũ bằng cách biến đổi từng phần tử qua hàm callback. |
| **`findIndex`** | Phương thức tìm vị trí của phần tử đầu tiên thỏa mãn điều kiện; trả về $-1$ nếu không tìm thấy. |

### Bài tập

- Cho mảng `fruits` ban đầu: `['cam', 'xoài', 'nho', 'táo', 'cam']`.
- **Nhiệm vụ:** Tạo một mảng mới biến đổi mỗi phần tử chuỗi ban đầu thành một chuỗi mới có kèm dấu chấm than ở cuối, ví dụ:  
  `'cam'` $\rightarrow$ `'cam!'`
- **Đề nghị:** Sử dụng phương thức `map()` kết hợp với hàm mũi tên (**Arrow Function**) để giải quyết bài toán một cách ngắn gọn.

### Kết luận

- **Mảng trong JavaScript rất linh hoạt và đa dụng**, hỗ trợ lưu trữ nhiều kiểu dữ liệu lồng nhau và thực hiện các phép biến đổi cấu trúc phức tạp.
- Nắm vững cách **khai báo**, **truy cập phần tử**, và tận dụng tốt các **phương thức tối ưu như `push()`, `map()`, `findIndex()`** giúp nâng cao hiệu suất xử lý dữ liệu.
- Arrow Function là một **kỹ thuật quan trọng giúp viết mã nguồn ngắn gọn, tường minh khi kết hợp cùng các phương thức duyệt mảng**.
