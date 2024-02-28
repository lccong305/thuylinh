# Tym-TQ

TỔNG HỢP CODE TRÁI TIM THỦ KHOA LÝ 

CODE được viết trên 2 ngôn ngữ HTML và PYTHON

Với HTML các bạn chỉ cần truy cập https://www.w3schools.com/tryit/ và Run.

Với PYTHON các bạn phải sử dụng Phần mềm đọc/viết mã code (Visual Studio, Notepad++, Python, Clion,...)

---
id: Logic
title: Các file xử lý
sidebar_label: Các file xử lý
---

## Những thông tin cần thiết
- Cấu trúc và các lớp đối tượng
```cs
    File: OrderPaymentRegister.cs
    Method: ExecOrderPayment
    => Nơi chứa những xử lý liên kết xác nhận/đăng ký payment qua API

    File: OrderCommon_OrderCancel.cs
    Method: CancelExternalCooperationPayment
    => Chứa những liên kết xử lý liên kết payment qua API
```
### Xử lý payment K38
- Tại OrderPaymentRegister method ExecOrderPayment
- ExecPaymentGmoKb thực hiện quy trình thanh toán sử dụng cổng thanh toán GMO
<ModalViewImage src='img/Payments/K38/func/handle1.png' />
## Mô tả

Hàm này thực hiện việc xử lý thanh toán sử dụng cổng thanh toán GMO KB (GMO Payment Gateway - KB) cho một đơn hàng cụ thể.

## Đối số

- `order`: Một Hashtable chứa thông tin về đơn hàng.
- `cart`: Một đối tượng CartObject đại diện cho giỏ hàng của người dùng.

## Giá trị trả về

Kiểu dữ liệu `bool`: True nếu thanh toán được thực hiện thành công, False nếu có bất kỳ lỗi nào xảy ra trong quá trình thanh toán.

## Lưu ý

- Hàm này được thiết kế để được sử dụng trong một ứng dụng thương mại điện tử để thực hiện các giao dịch thanh toán.
- Đảm bảo rằng các hằng số được sử dụng trong hàm đã được định nghĩa trước đó.

## Các bước thực hiện

1. Tạo một đối tượng `GmoTransactionApi` để tương tác với API của GMO KB.
2. Tạo một mã đặt hàng thanh toán sử dụng hàm `CreatePaymentOrderId` từ lớp `OrderCommon`.
3. Tạo một yêu cầu giao dịch mới thông qua đối tượng `GmoRequestTransactionRegister`, truyền thông tin giỏ hàng `cart` vào.
4. Nếu có thông tin HTTP Header cần gửi trong yêu cầu và tùy chọn được bật, thêm thông tin này vào yêu cầu.
5. Gửi yêu cầu giao dịch đến cổng thanh toán GMO KB thông qua đối tượng `facade`.
6. Kiểm tra kết quả trả về từ cổng thanh toán:
   - Nếu không có kết quả nào được nhận được, thêm thông báo lỗi và cập nhật thông điệp lỗi API.
   - Nếu có lỗi từ cổng thanh toán, thêm thông báo lỗi và cập nhật thông điệp lỗi API.
   - Nếu có lỗi hoặc cảnh báo từ cổng thanh toán hoặc không tạo được dữ liệu đơn hàng, thêm thông báo lỗi và cập nhật thông điệp lỗi API.
7. Nếu giao dịch đang được xem xét hoặc chờ tiền gửi, cập nhật trạng thái thanh toán của đơn hàng tương ứng và trả về True.
8. Nếu thanh toán được xác nhận thành công, cập nhật thông tin giao dịch trong đơn hàng và trả về True.

## Lưu ý quan trọng

- Hàm này phụ thuộc vào các phương thức và lớp từ một thư viện hoặc mã nguồn bên ngoài như `GmoTransactionApi`, `OrderCommon`, và các hằng số từ `Constants`. Cần đảm bảo rằng các phương thức và lớp này đã được định nghĩa và cấu hình đúng cách trước khi sử dụng hàm này.

<ModalViewImage src='img/Payments/K38/func/handle2.png' />
<ModalViewImage src='img/Payments/K38/func/handle3.png' />
