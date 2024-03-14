| 5         | Tên khu vực vận chuyển            | shipping_zone_name             | nvarchar     | 30            | ○            | N''              |          | *Chỉ áp dụng cho địa chỉ giao hàng đặc biệt                     |
| 6         | Mã bưu điện                       | zip                            | ntext        |               | ○            | N''              |          | "Mã bưu điện có dấu gạch nối phân cách bằng dấu phẩy
                                                                                                                                     |
| 7         | Phí vận chuyển sản phẩm kích cỡ XXS| size_xxs_shipping_price       | decimal      | 18,3          | ○            | 0                |          | "Phí vận chuyển kích cỡ XXS
                                                                                                                      "                                                               |
| 8         | Phí vận chuyển sản phẩm kích cỡ XS | size_xs_shipping_price        | decimal      | 18,3          | ○            | 0                |          | "Phí vận chuyển kích cỡ XS
                                                                                                                      "                                                               |
| 9         | Phí vận chuyển sản phẩm kích cỡ S  | size_s_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ S                                      |
| 10        | Phí vận chuyển sản phẩm kích cỡ M  | size_m_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ M                                      |
| 11        | Phí vận chuyển sản phẩm kích cỡ L  | size_l_shipping_price         | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ L                                      |
| 12        | Phí vận chuyển sản phẩm kích cỡ XL | size_xl_shipping_price        | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ XL                                     |
| 13        | Phí vận chuyển sản phẩm kích cỡ XXL| size_xxl_shipping_price       | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ XXL                                    |
| 14        | Cờ xóa                             | del_flg                        | nvarchar     | 1             | ○            | N'0'             |          | "Đánh dấu xóa.
                                                                                                                      0: Bình thường
                                                                                                                      1: Đã xóa"                                                     |
| 15        | Ngày tạo                           | date_created                   | datetime     |               | ○            | getdate()        |          |                                                               |
| 16        | Ngày chỉnh sửa                     | date_changed                   | datetime     |               | ○            | getdate()        |          |                                                               |
| 17        | Người chỉnh sửa cuối cùng         | last_changed                   | nvarchar     | 20            | ○            | N''              |          | Tên người thực hiện cập nhật                                  |
| 18        | Phí vận chuyển sản phẩm kích cỡ thư | size_mail_shipping_price      | decimal      | 18,3          | ○            | 0                |          | Phí vận chuyển kích cỡ thư                                    |
| 19        | Ngưỡng phí vận chuyển có điều kiện| conditional_shipping_price_threshold | decimal | 18,3          |               |                  |          | "NULL: Không thay đổi phí vận chuyển
                                                                                                                      Số khác NULL: Nếu số tiền mua hàng đạt được số này
                                                                                                                      Phí vận chuyển sẽ được thay thế bằng giá trị của conditional_shipping_price" |
| 20        | Phí vận chuyển có điều kiện        | conditional_shipping_price    | decimal      | 18,3          |               |                  |          |                                                               |
| 21        | Cờ khu vực giao hàng không khả dụng| unavailable_shipping_area_flg | nvarchar     | 1             | ○            | N'0'             |          | "0: Không chỉ định khu vực giao hàng không khả dụng
                                                                                                                      1: Chỉ định khu vực giao hàng không khả dụng"                   |
| 22        | Phạm vi nhiệt độ vận chuyển       | shipping_temperature_range     | nvarchar     | 1             | ○            | N'0'             | 5        | "Lưu trữ ph
