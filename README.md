### Bảng `w2_ShortUrl`

:::important

+ **default**: Giá trị mặc định (default value)
+ **getdate()**: Hàm lấy giá trị ngày hiện tại
+ **N**: Tiền tố N được dùng để khai báo kiểu nvarchar trong sql. Ví dụ: khai báo id người dùng là user1 => câu lệnh là `INSERT INTO w2_ShopShippingZone (shop_id) VALUE (N'Shop1')`

:::important

**Cấu trúc bảng:**

| Tên cột        | Kiểu dữ liệu | Giới hạn     | Giá trị mặc định | Mô tả                                |
|----------------|--------------|--------------|------------------|--------------------------------------|
| surl_no        | bigint       | NOT NULL     |                  | Số thứ tự của URL rút gọn  |
| shop_id        | nvarchar(10) | NOT NULL     | ''               | ID cửa hàng                          |
| short_url      | nvarchar(255)| NOT NULL     | ''               | URL rút gọn                          |
| long_url       | nvarchar(2000)| NOT NULL    | ''               | URL dài                             |
| date_created   | datetime     | NOT NULL     | getdate()        | Ngày tạo                             |
| date_changed   | datetime     | NOT NULL     | getdate()        | Ngày chỉnh sửa                       |
| last_changed   | nvarchar(20) | NOT NULL     | ''               | Người chỉnh sửa cuối cùng           |

**Khóa chính:** `surl_no`

**Chỉ mục:** `shop_id`, `short_url`

```sql
SELECT TABLE_CATALOG, TABLE_NAME, COLUMN_NAME, ORDINAL_POSITION, IS_NULLABLE, DATA_TYPE, CHARACTER_MAXIMUM_LENGTH, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'w2_ShortUrl'
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
