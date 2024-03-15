## Bảng w2_OperatorAuthority

Bảng này lưu trữ quyền của các nhà điều hành cho các cửa hàng khác nhau.

### Cấu trúc Bảng:

| Tên Cột        | Kiểu Dữ Liệu | Mô Tả                                     |
|----------------|--------------|-------------------------------------------|
| shop_id        | nvarchar(10) | Định danh cho cửa hàng.                  |
| operator_id    | nvarchar(20) | Định danh cho nhà điều hành.             |
| condition_type | nvarchar(30) | Loại điều kiện cho quyền.                |
| permission     | nvarchar(1)  | Quyền được cấp cho nhà điều hành.        |
| condition_value| nvarchar(30) | Giá trị liên kết với loại điều kiện.     |

### Ràng Buộc:

- **PK_w2_OperatorAuthority**: Ràng buộc khóa chính trên (`shop_id`, `operator_id`, `condition_value`).

### Chỉ mục:

- **IX_w2_OperatorAuthority_1**: Chỉ mục trên (`shop_id`, `operator_id`, `condition_type`).

