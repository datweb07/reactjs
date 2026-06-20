# [React JS] Cách Chia Nhỏ Component Để Quản Lý Dự Án Lớn

## 1. Đặt vấn đề

Trong các buổi học trước, chúng ta viết toàn bộ các Component như `Header`, `MainContent` chung vào trong file `App.jsx`. Khi dự án phát triển ngày càng lớn, số lượng Component tăng lên sẽ khiến file `App.jsx` trở nên quá dài, rối mắt và rất khó bảo trì.

Vì vậy, tư duy lập trình React thực tế yêu cầu chúng ta phải tách mỗi Component ra thành một file riêng biệt để dễ dàng phát triển và quản lý.

## 2. Cấu trúc thư mục chuẩn sau khi tách

Chúng ta sẽ tạo một thư mục quản lý tập trung có tên là `components` nằm bên trong thư mục `src`. Mỗi Component con sẽ có một thư mục riêng đặt trùng tên (viết hoa chữ cái đầu), bên trong chứa file `.jsx` tương ứng:

```text
src/
└── components/
    ├── Header/
    │   └── Header.jsx
    └── MainContent/
        └── MainContent.jsx

```

## 3. Các bước thực hiện tách Component chi tiết

### Bước 1: Dọn dẹp file `App.jsx`

* Xóa bỏ các lệnh `import` hình ảnh riêng lẻ không còn dùng (vì đã chuyển qua mảng dữ liệu).
* Xóa bỏ các lệnh `console.log()` kiểm tra dữ liệu để code gọn gàng.

### Bước 2: Tách Component `Header`

1. Tạo thư mục `Header` trong `src/components/`.
2. Tạo file `Header.jsx`.
3. Cắt (`Ctrl + X`) hàm `function Header()` từ file `App.jsx` sang file mới.
4. Di chuyển dòng `import logo from ...` sang file `Header.jsx`.

> **Lưu ý sửa đường dẫn (Relative Path):** Vì vị trí file đã thay đổi (nằm sâu hơn 2 cấp), ta phải dùng cú pháp `../../` để lùi ra ngoài thư mục `src` trước khi đi vào `assets`:
> ```jsx
> import logo from '../../assets/logo.png'; 
> 
> ```
> 
> 

5. Xuất Component ra để file khác có thể dùng bằng `export default`:

```jsx
// File: src/components/Header/Header.jsx
import React from 'react';
import logo from '../../assets/logo.png';

function Header() {
    return (
        <header>
            <img src={logo} alt="Logo" />
        </header>
    );
}

export default Header;

```

### Bước 3: Tách Component `MainContent`

1. Tạo thư mục `MainContent` trong `src/components/`.
2. Tạo file `MainContent.jsx`.
3. Cắt (`Ctrl + X`) hàm `function MainContent()` từ file `App.jsx` sang.
4. Cắt dòng `import PropTypes from 'prop-types';` và phần định nghĩa xác thực `MainContent.propTypes` sang file mới này để tránh lỗi thiếu thư viện.
5. Thực hiện `export default` component:

```jsx
// File: src/components/MainContent/MainContent.jsx
import React from 'react';
import PropTypes from 'prop-types';

function MainContent({ image, title, desc }) {
    return (
        <li>
            <img src={image} alt={title} />
            <h2>{title}</h2>
            <p>{desc}</p>
        </li>
    );
}

MainContent.propTypes = {
    image: PropTypes.string.isRequired,
    title: PropTypes.string.isRequired,
    desc: PropTypes.string
};

export default MainContent;

```

## 4. Cập nhật lại file `App.jsx` sau khi tối ưu

Sau khi đã di chuyển các khối mã sang file riêng, tại file chính `App.jsx`, chúng ta chỉ cần thực hiện `import` lại hai component này để sử dụng. Mã nguồn lúc này sẽ vô cùng ngắn gọn và trực quan:

```jsx
// File: src/App.jsx
import React from 'react';
import Header from './components/Header/Header.jsx';
import MainContent from './components/MainContent/MainContent.jsx';
import { MyData } from '../data.js';

function App() {
    return (
        <>
            <Header />
            <main id="core-concept">
                <ul>
                    <MainContent {...MyData[0]} />
                    <MainContent {...MyData[1]} />
                    <MainContent {...MyData[2]} />
                    <MainContent {...MyData[3]} />
                </ul>
            </main>
        </>
    );
}

export default App;

```
