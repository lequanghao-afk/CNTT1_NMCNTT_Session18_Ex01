# Bài 1 : Sự cố không truy cập được hệ thống quản trị
**1. PHÂN TÍCH**



-   Input: Tên miền `phong-dieu-phoi.grenlog.vn`.
    
-   Output: Địa chỉ IP của máy chủ.
    
-   DNS có nhiệm vụ chuyển đổi tên miền thành địa chỉ IP.

-Sơ đồ:

`Tên miền → DNS Resolver → Root DNS → TLD DNS → Authoritative DNS → Địa chỉ IP`

## PHẦN 2. TRIỂN KHAI
Nếu nhận được mã HTTP Status Code thì yêu cầu đã đến một máy chủ HTTP. Nếu báo `DNS_PROBE_FINISHED_NXDOMAIN` thì tên miền chưa phân giải được IP, yêu cầu chưa đến máy chủ đích.

## PHẦN 3. KIỂM THỬ

Tình huống: Sửa đúng tên miền nhưng nhận lỗi `404 Not Found`.

Nguyên nhân:

-   Đường dẫn URL không tồn tại.
    
-   Trang quản trị đã bị xóa hoặc di chuyển.
    
-   Cấu hình đường dẫn trên máy chủ bị sai.
    

Cách khắc phục:

1.  Kiểm tra lại URL.
    
2.  Xác nhận tài nguyên có tồn tại.
    
3.  Liên hệ bộ phận kỹ thuật kiểm tra máy chủ.

