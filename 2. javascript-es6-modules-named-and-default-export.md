### 2. JavaScript ES6 - Modules Tìm hiểu Named Export, Default Export - Giải thích chi tiết

### Khái niệm Module và Tính chất
- **Module** giúp chia nhỏ ứng dụng thành các phần nhỏ, dễ quản lý, bảo trì, kiểm thử.
- Giúp **tái sử dụng code** ở nhiều file khác nhau.
- Khi sử dụng module, cần thêm thuộc tính **`type="module"`** trong thẻ `<script>` khi nhúng file JavaScript.

### Hai cách export trong Module ES6

1. **Named Export (Xuất có tên):**
   - Cho phép export **nhiều phần tử** (biến, hàm, class) từ cùng một file.
   - Cách viết:
     - Khai báo biến/hàm/class bình thường rồi dùng `export { name1, name2, ... }`.
     - Hoặc dùng `export` ngay ở đầu khai báo (ví dụ: `export const myVar = 10;`).
   - Ví dụ khai báo:
     ```javascript
     const maVa = 10;
     function myFunction() { console.log("Xin chào"); }
     export { maVa, myFunction };
     ```

2. **Default Export (Xuất mặc định):**
   - Mỗi module chỉ được có **1 export mặc định duy nhất**.
   - Dùng để export một biến, hàm hoặc class.
   - Cách viết:
     ```javascript
     const df = "default";
     export default df;
     ```
   - Khi import, không cần dùng ngoặc nhọn và có thể đặt tên bất kỳ.

### Cách Import trong Module ES6
- Khi sử dụng trong file khác, phải khai báo:
```html
  <script type="module" src="main.js"></script>

```

* Các cách import:
1. **Import named export:** - Dùng ngoặc nhọn để liệt kê tên các phần tử cần sử dụng.
* Ví dụ:
```javascript
import { maVa, myFunction } from './name.js';

```

2. **Import tất cả named export dưới dạng đối tượng:** - Dùng cú pháp `import * as nameAlias from './name.js';`
* Sử dụng: `nameAlias.maVa`, `nameAlias.myFunction()`.
* Đây là đối tượng gom tất cả các phần tử exported.


3. **Import default export:** - Không dùng ngoặc nhọn và đặt tên tùy ý:
```javascript
import df from './default.js';

```

4. **Kết hợp import named export và default export:**
* **Lưu ý:** Default export không được gom trong `import * as obj` của named export, nên nếu cần dùng phải import riêng biệt.

### Các điểm lưu ý quan trọng

* **Mỗi module chỉ có một default export**, không thể có nhiều default export trong cùng một file.
* Nếu file **đồng thời có named export và default export**, khi import tất cả named export bằng `import * as name`, **default export không nằm trong đối tượng đó** mà phải import riêng.
* **Đổi tên khi import:** - Với default export, tên đặt tùy ý.
* Với named export, dùng cú pháp:
```javascript
import { maVa as maVaAlias } from './name.js';

```

* Module được sử dụng phổ biến trong dự án lớn, đặc biệt trong React với việc tổ chức và tái sử dụng các phần tử code.

### Ví dụ tổng quát về khai báo và sử dụng module

| Phương pháp xuất (export) | Ví dụ khai báo | Cách import sử dụng |
| --- | --- | --- |
| Named Export | `export const x = 10; export function foo() {}` | `import { x, foo } from './file.js';` |
| Named Export (liệt kê) | `const x = 10; function foo() {}; export { x, foo };` | `import { x, foo } from './file.js';` |
| Import tất cả named export | - | `import * as file from './file.js'; file.x;` |
| Default Export | `const df = 20; export default df;` | `import df from './file.js';` |
| Import đổi tên named export | - | `import { x as xAlias } from './file.js';` |
| Import đổi tên default export | - | `import anyName from './file.js';` |

### Key insights

* **Module là công cụ phân chia code giúp quản lý tốt trong ứng dụng lớn.**
* **Named export cho phép xuất nhiều thành phần, default export chỉ một thành phần duy nhất.**
* **Khi import, default export không cần dùng ngoặc nhọn và có thể đặt tên tùy ý. Named export cần dùng ngoặc nhọn và có thể đổi tên bằng alias.**
* **Import tất cả named export bằng `import * as obj` không bao gồm default export.**
* **Sử dụng module trong React giúp tái sử dụng code và giảm sự phụ thuộc phức tạp.**
