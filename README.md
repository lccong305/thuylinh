# Bảng w2_UserManagementLevel

Bảng này lưu trữ thông tin liên quan đến các cấp quản lý người dùng.

:::important

+ **default**: Giá trị mặc định (default value)
+ **GETDATE()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo last_changed là w2_user  <br/> => câu lệnh là `INSERT INTO w2_UserManagementLevel (last_changed) VALUE (N'w2_user')`

:::

## Cấu trúc Bảng

| Tên Cột                 | Kiểu Dữ Liệu    | Giá Trị Mặc Định | Mô Tả                                                         |
|--------------------------|-----------------|-------------------|--------------------------------------------------------------|
| seq_no                   | bigint          |                   | Định danh duy nhất cho mỗi bản ghi, được tạo tự động.       |
| user_management_level_id | nvarchar(30)    |                   | Định danh duy nhất cho cấp quản lý người dùng.              |
| user_management_level_name | nvarchar(100) | ''              | Tên của cấp quản lý người dùng.                              |
| display_order            | int             | 1                 | Thứ tự hiển thị của các cấp quản lý người dùng.             |
| date_created             | datetime        | getdate()      | Ngày và giờ khi bản ghi được tạo.                           |
| date_changed             | datetime        | getdate()       | Ngày và giờ khi bản ghi được thay đổi lần cuối.             |
| last_changed             | nvarchar(20)    | ''              | Định danh cho người dùng đã thay đổi bản ghi cuối cùng.     |

## Ràng Buộc

- **PK_w2_UserManagementLevel**: Ràng buộc khóa chính trên cột `user_management_level_id`.

## Chỉ Mục

- **IX_w2_UserManagementLevel_1**: Chỉ mục trên cột `display_order`.

- Nếu bạn muốn biết dữ liệu của bảng **w2_UserManagementLevel** gồm những cột nào, mỗi cột sẽ mang kiểu dữ liệu gì, độ dài bao nhiêu, được phép null hay không và giá trị mặc định khi null là gì,... thì có thể chạy mẫu câu SQL sau :

```sql
SELECT TABLE_CATALOG, TABLE_NAME, COLUMN_NAME, ORDINAL_POSITION, IS_NULLABLE, DATA_TYPE, CHARACTER_MAXIMUM_LENGTH, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'w2_UserManagementLevel'
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
