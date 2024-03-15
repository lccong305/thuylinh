### Bảng `w2_ShortUrl`

Bảng này lưu trữ thông tin về các URL rút gọn được tạo ra cho các cửa hàng.

**Cấu trúc bảng:**

| Tên cột        | Kiểu dữ liệu | Giới hạn     | Giá trị mặc định | Mô tả                                |
|----------------|--------------|--------------|------------------|--------------------------------------|
| surl_no        | bigint       | NOT NULL     |                  | Số thứ tự duy nhất của URL rút gọn  |
| shop_id        | nvarchar(10) | NOT NULL     | ''               | ID cửa hàng                          |
| short_url      | nvarchar(255)| NOT NULL     | ''               | URL rút gọn                          |
| long_url       | nvarchar(2000)| NOT NULL    | ''               | URL dài                             |
| date_created   | datetime     | NOT NULL     | getdate()        | Ngày tạo                             |
| date_changed   | datetime     | NOT NULL     | getdate()        | Ngày chỉnh sửa                       |
| last_changed   | nvarchar(20) | NOT NULL     | ''               | Người chỉnh sửa cuối cùng           |

**Khóa chính:** `surl_no`

**Chỉ mục:** `shop_id`, `short_url`
