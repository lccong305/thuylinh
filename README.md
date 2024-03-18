## Bảng w2_UserIntegrationUser

Bảng này lưu trữ người dùng trong quá trình tích hợp người dùng.

:::important

+ **default**: Giá trị mặc định (default value)
+ **GETDATE()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo last_changed là w2_user  <br/> => câu lệnh là `INSERT INTO w2_UserIntegrationUser (last_changed) VALUE (N'w2_user')`

:::

### Cấu trúc Bảng:

| Tên Cột              | Kiểu Dữ Liệu | Giá Trị Mặc Định | Mô Tả                                      |
|----------------------|--------------|------------------|--------------------------------------------|
| user_integration_no  | bigint       |                  | Số duy nhất cho tích hợp người dùng.     |
| user_id              | nvarchar(30) |                  | Định danh của người dùng.                 |
| representative_flg   | nvarchar(1)  | '0'              | Cờ đại diện (0: Không phải, 1: Đại diện).|
| date_created         | datetime     | getdate()        | Ngày và giờ tạo bản ghi.                  |
| date_changed         | datetime     | getdate()        | Ngày và giờ thay đổi bản ghi.            |
| last_changed         | nvarchar(20) |                  | Người thay đổi cuối cùng.                 |

### Ràng Buộc:

- **PK_w2_UserIntegrationUser**: Ràng buộc khóa chính trên (`user_integration_no`, `user_id`).

### Chỉ mục:

- **IX_w2_UserIntegrationUser_1**: Chỉ mục trên (`user_id`).


- Nếu bạn muốn biết dữ liệu của bảng **w2_UserIntegrationUser** gồm những cột nào, mỗi cột sẽ mang kiểu dữ liệu gì, độ dài bao nhiêu, được phép null hay không và giá trị mặc định khi null là gì,... thì có thể chạy mẫu câu SQL sau :

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
