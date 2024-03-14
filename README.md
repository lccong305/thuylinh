| Số thứ tự | Tên cột                             | Tên cột (Tiếng Anh)            | Kiểu dữ liệu | Độ dài ký tự | Giá trị rỗng | Giá trị mặc định | Duy nhất | Giải thích                                                    |
|-----------|-------------------------------------|--------------------------------|--------------|---------------|--------------|------------------|----------|---------------------------------------------------------------|
| 1         | ID cửa hàng                         | shop_id                        | nvarchar     | 10            | ○            | N''              |          |                                                               |
| 2         | ID cài đặt phí vận chuyển          | shipping_id                    | nvarchar     | 10            | ○            | N''              |          |                                                               |
| 3         | ID công ty vận chuyển              | delivery_company_id            | nvarchar     | 10            | ○            | N''              |          |                                                               |
| 4         | Phân loại khu vực vận chuyển      | shipping_zone_no               | int          |               | ○            | N'0'             |          | "0: Phân loại cơ bản (không xem xét thông tin khu vực)
                                                                                                                      1~47: Cài đặt tỉnh thành
                                                                                                                      48~: Cài đặt địa chỉ giao hàng đặc biệt"                        |
| 5         | Tên khu vực vận chuyển            | shipping_zone_name             | nvarchar     | 30            | ○            | N''              |          | *Chỉ áp dụng cho địa chỉ giao hàng đặc biệt                     |
| 6         | Mã bưu điện                       | zip                            | ntext        |               | ○            | N''              |          | "Mã bưu điện có dấu gạch nối phân cách bằng dấu phẩy
                                                                                                                      *Chỉ áp dụng cho địa chỉ giao hàng đặc biệt"                    |
| 7         | Phí vận chuyển sản phẩm kích cỡ XXS| size_xxs_shipping_price       | decimal      | 18,3          | ○            | 0                |          | "Phí vận chuyển kích cỡ XXS
                                                                                                                      "                                                               |
| 8         | Phí vận chuyển sản phẩm kích cỡ XS | size_xs_shipping_price        | decimal      | 18,3          | ○            | 0                |          | "Phí vận chuyển kích cỡ XS
                                                                                                                      "                                                               |
| 9         | Phí vận chuyển sản phẩm kích cỡ S  | size_s_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ S                                      |
| 10        | Phí vận chuyển sản phẩm kích cỡ M  | size_m_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ M                                      |
| 11        | Phí vận chuyển sản phẩm kích cỡ L  | size_l_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ L                                      |
| 
