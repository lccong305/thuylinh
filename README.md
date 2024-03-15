## Bảng w2_OperatorAuthority

Bảng này lưu trữ quyền của các nhà điều hành cho các cửa hàng khác nhau.

:::important

+ **default**: Giá trị mặc định (default value)
+ **getdate()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo id người dùng là user1 => câu lệnh là `INSERT INTO w2_OperatorAuthority (shop_id) VALUE (N'url1')`

:::

### Cấu trúc Bảng:

| Tên Cột        | Kiểu Dữ Liệu | Giá Trị Mặc Định | Mô Tả                                     |
|----------------|--------------|------------------|-------------------------------------------|
| shop_id        | nvarchar(10) | ''               | Định danh cho cửa hàng.                  |
| operator_id    | nvarchar(20) | ''               | Định danh cho nhà điều hành.             |
| condition_type | nvarchar(30) | ''               | Loại điều kiện cho quyền.                |
| permission     | nvarchar(1)  | '0'              | Quyền được cấp cho nhà điều hành.        |
| condition_value| nvarchar(30) | ''               | Giá trị liên kết với loại điều kiện.     |

### Ràng Buộc:

- **PK_w2_OperatorAuthority**: Ràng buộc khóa chính trên (`shop_id`, `operator_id`, `condition_value`).

### Chỉ mục:

- **IX_w2_OperatorAuthority_1**: Chỉ mục trên (`shop_id`, `operator_id`, `condition_type`).

```sql
SELECT TABLE_CATALOG, TABLE_NAME, COLUMN_NAME, ORDINAL_POSITION, IS_NULLABLE, DATA_TYPE, CHARACTER_MAXIMUM_LENGTH, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'w2_OperatorAuthority'
```

* Trong đó :

- TABLE_CATALOG : tên database
- TABLE_NAME : tên table
- COLUMN_NAME : tên cột
- ORDINAL_POSITION : vị trí khai báo hoặc hiển thị của cột (nhất là khi bạn "SELECT *")
- IS_NULLABLE : cột giá trị cho phép null hay không?
- DATA_TYPE : kiểu dữ liệu của cột
- COLUMN_DEFAULT : giá trị mặc định của cột
- CHARACTER_MAXIMUM_LENGTH : độ dài dữ liệu của cột
