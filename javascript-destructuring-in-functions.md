Trong lập trình JavaScript (đặc biệt là khi làm việc với ReactJS), Destructuring thường được sử dụng trực tiếp ngay tại tham số (parameter) của hàm. Cách làm này giúp code ngắn gọn, rõ ràng và tránh việc lặp đi lặp lại thao tác truy cập thuộc tính thông qua đối tượng (`object.property`) bên trong thân hàm.

Giả sử chúng ta có một đối tượng đơn hàng như sau:

```javascript
const donHang = {
    maDonHang: 101,
    tienTe: "VND",
    tongTien: 50000
};

```

## 1. So sánh khi KHÔNG sử dụng và CÓ sử dụng Destructuring

### Trường hợp 1: Không sử dụng Destructuring

Khi truyền một object vào hàm theo cách truyền thống, bạn phải nhận toàn bộ object đó làm tham số, sau đó tạo các biến cục bộ hoặc gọi trực tiếp bằng cú pháp dấu chấm (`.`).

```javascript
function xuLyDonHang(donHang) {
    // Phải mất 3 dòng để tạo biến trích xuất thuộc tính
    const maDonHang = donHang.maDonHang; 
    const tienTe = donHang.tienTe;
    const tongTien = donHang.tongTien;

    // Hoặc sử dụng trực tiếp donHang.maDonHang trong chuỗi
    console.log(`Mã đơn hàng: ${maDonHang}`);
    console.log(`Tiền tệ: ${tienTe}`);
    console.log(`Tổng tiền: ${tongTien}`);
}

// Gọi hàm
xuLyDonHang(donHang);

```

*Nhược điểm:* Code bị dài dòng, lặp lại cú pháp `donHang.` nhiều lần để lấy dữ liệu.

### Trường hợp 2: Có sử dụng Destructuring

Thay vì nhận tham số là một biến đại diện cho object, ta sử dụng cú pháp ngoặc nhọn `{}` ngay tại phần khai báo tham số của hàm để bóc tách thẳng các thuộc tính cần dùng.

```javascript
// Trích xuất trực tiếp thuộc tính tại tham số của hàm
function xuLyDonHang2({ maDonHang, tienTe, tongTien }) {
    // Có thể sử dụng trực tiếp các thuộc tính như một biến độc lập
    console.log(`Mã đơn hàng: ${maDonHang}`);
    console.log(`Tiền tệ: ${tienTe}`);
    console.log(`Tổng tiền: ${tongTien}`);
}

// Gọi hàm với đối tượng donHang
xuLyDonHang2(donHang);

```

*Ưu điểm:* Code ngắn gọn hơn, loại bỏ được việc khai báo gán biến trung gian trong thân hàm.

> **Lưu ý:** Tên các thuộc tính trong ngoặc nhọn `{}` bắt buộc phải trùng khớp với các `key` hiện có trong object truyền vào.

## 2. Destructuring kết hợp với giá trị mặc định (Default Values)

Trong nhiều trường hợp thực tế, object truyền vào hàm có thể bị thiếu một vài thuộc tính. Để tránh lỗi hoặc dữ liệu bị trả về `undefined`, ta có thể gán giá trị mặc định cho thuộc tính ngay khi phá cấu trúc tham số bằng dấu bằng (`=`).

```javascript
function xuLyDonHangMaccDinh({ maDonHang = 0, tienTe = "VND", tongTien = 0 }) {
    console.log(`Mã đơn hàng: ${maDonHang}`);
    console.log(`Tiền tệ: ${tienTe}`);
    console.log(`Tổng tiền: ${tongTien}`);
}

// Gọi hàm với một object bị khuyết thuộc tính tienTe và tongTien
xuLyDonHangMaccDinh({ maDonHang: 102 });

// Kết quả Output:
// Mã đơn hàng: 102
// Tiền tệ: VND (Lấy giá trị mặc định)
// Tổng tiền: 0 (Lấy giá trị mặc định)

```

## 3. Destructuring kết hợp với Rest Parameter (`...`)

Nếu bạn chỉ muốn bóc tách một vài thuộc tính cụ thể, còn các thuộc tính khác (chưa biết trước hoặc không cần dùng ngay) muốn gom lại thành một object riêng, bạn có thể dùng toán tử Rest (`...`).

```javascript
function xuLyDonHangRest({ maDonHang, ...rest }) {
    console.log(`Mã đơn hàng tách riêng: ${maDonHang}`);
    
    // Biến 'rest' sẽ gom tất cả thuộc tính còn lại thành một đối tượng mới
    console.log("Các thuộc tính còn lại:", rest);
}

// Gọi hàm với object nhiều thuộc tính
xuLyDonHangRest({
    maDonHang: 103,
    tienTe: "USD",
    tongTien: 1000,
    khachHang: "Nguyễn Văn A"
});

// Kết quả Output:
// Mã đơn hàng tách riêng: 103
// Các thuộc tính còn lại: { tienTe: 'USD', tongTien: 1000, khachHang: 'Nguyễn Văn A' }

```

## 4. Sử dụng tên bí danh (Alias) cho thuộc tính

Nếu thuộc tính của object quá dài hoặc trùng với một biến khác có sẵn trong thân hàm, bạn có thể đổi tên (đặt danh tính mới) cho biến đó bằng cú pháp `tênThuộcTính: tênBíDanh`.

```javascript
function xuLyDonHangAlias({ maDonHang: ma, ...rest }) {
    // Từ lúc này, trong thân hàm ta dùng biến 'ma' thay cho 'maDonHang'
    console.log(`Mã đơn hàng (dùng tên ngắn): ${ma}`);
    console.log("Phần còn lại:", rest);
}

// Gọi hàm
xuLyDonHangAlias({
    maDonHang: 103,
    tienTe: "USD",
    tongTien: 1000,
    khachHang: "Nguyễn Văn A"
});

```
