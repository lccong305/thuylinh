## Bảng w2_UserIntegration

Bảng này lưu trữ tích hợp người dùng.

:::important

+ **default**: Giá trị mặc định (default value)
+ **getdate()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo id shop là shop1  <br/> => câu lệnh là `INSERT INTO w2_UserIntegration (last_changed) VALUE (N'w2_user')`

:::

### Cấu trúc Bảng:

| Tên Cột              | Kiểu Dữ Liệu | Giá Trị Mặc Định | Mô Tả                            |
|----------------------|--------------|------------------|----------------------------------|
| user_integration_no  | bigint       |                  | Số duy nhất cho tích hợp người dùng. |
| status               | nvarchar(10) |                  | Trạng thái của tích hợp.               |
| date_created         | datetime     | getdate()        | Ngày và giờ tạo bản ghi.             |
| date_changed         | datetime     | getdate()        | Ngày và giờ thay đổi bản ghi.       |
| last_changed         | nvarchar(20) |                  | Người thay đổi cuối cùng.            |

### Ràng Buộc:

- **PK_w2_UserIntegration**: Ràng buộc khóa chính trên (`user_integration_no`).

### Chỉ mục:

- **IX_w2_UserIntegration_1**: Chỉ mục trên (`status`).

- ```sql
SELECT TABLE_CATALOG, TABLE_NAME, COLUMN_NAME, ORDINAL_POSITION, IS_NULLABLE, DATA_TYPE, CHARACTER_MAXIMUM_LENGTH, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'w2_UserIntegration'
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
