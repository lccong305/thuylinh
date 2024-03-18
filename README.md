## Bảng w2_UserIntegrationHistory

Bảng này lưu trữ lịch sử tích hợp người dùng.

:::important

+ **default**: Giá trị mặc định (default value)
+ **GETDATE()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo last_changed là w2_user  <br/> => câu lệnh là `INSERT INTO w2_UserIntegrationHistory (last_changed) VALUE (N'w2_user')`

:::

### Cấu trúc Bảng:

| Tên Cột            | Kiểu Dữ Liệu | Giá Trị Mặc Định | Mô Tả                                          |
|--------------------|--------------|------------------|------------------------------------------------|
| user_integration_no| bigint       |                  | Số duy nhất cho tích hợp người dùng.         |
| user_id            | nvarchar(30) |                  | Định danh của người dùng.                     |
| branch_no          | int          | 1                | Số nhánh.                                     |
| table_name         | nvarchar(50) |                  | Tên bảng liên quan.                           |
| primary_key1       | nvarchar(100)|                  | Khóa chính 1.                                 |
| primary_key2       | nvarchar(100)|                  | Khóa chính 2.                                 |
| primary_key3       | nvarchar(100)|                  | Khóa chính 3.                                 |
| primary_key4       | nvarchar(100)|                  | Khóa chính 4.                                 |
| primary_key5       | nvarchar(100)|                  | Khóa chính 5.                                 |
| date_created       | datetime     | getdate()        | Ngày và giờ tạo bản ghi.                     |
| date_changed       | datetime     | getdate()        | Ngày và giờ thay đổi bản ghi.               |
| last_changed       | nvarchar(20) |                  | Người thay đổi cuối cùng.                    |

### Ràng Buộc:

- **PK_w2_UserIntegrationHistory**: Ràng buộc khóa chính trên (`user_integration_no`, `user_id`, `branch_no`).

- Nếu bạn muốn biết dữ liệu của bảng **w2_UserIntegrationHistory** gồm những cột nào, mỗi cột sẽ mang kiểu dữ liệu gì, độ dài bao nhiêu, được phép null hay không và giá trị mặc định khi null là gì,... thì có thể chạy mẫu câu SQL sau :

```sql
SELECT TABLE_CATALOG, TABLE_NAME, COLUMN_NAME, ORDINAL_POSITION, IS_NULLABLE, DATA_TYPE, CHARACTER_MAXIMUM_LENGTH, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'w2_UserIntegrationHistory'
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
