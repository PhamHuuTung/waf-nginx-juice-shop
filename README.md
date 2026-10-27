\# Thực hành WAF trên Nginx



\## 1. Mục tiêu



Dựng Web Application Firewall (WAF) sử dụng Nginx, ModSecurity và OWASP Core Rule Set (CRS) để bảo vệ OWASP Juice Shop.



Thực hiện kiểm thử và so sánh request khi truy cập trực tiếp ứng dụng với request đi qua WAF.



\## 2. Công nghệ sử dụng



\- Docker Compose

\- Nginx

\- ModSecurity

\- OWASP CRS

\- OWASP Juice Shop



\## 3. Kiến trúc



\- Juice Shop: http://localhost:3000

\- WAF: http://localhost:8080

\- Backend của WAF: http://web:3000



Cổng 3000 dùng để kiểm thử trực tiếp; cổng 8080 dùng để kiểm thử qua WAF.



\## 4. Cách chạy



```powershell

docker compose up -d

docker compose ps

```



Xem log WAF:



```powershell

docker compose logs --since=10m waf

```



Dừng hệ thống:



```powershell

docker compose down

```



\## 5. Kịch bản kiểm thử



1\. Truy cập Juice Shop trực tiếp qua cổng 3000.

2\. Thử request đăng nhập có dấu hiệu SQL Injection trong môi trường thực hành cục bộ.

3\. Lặp lại request qua cổng 8080.

4\. Kiểm tra log để xác định luật CRS khớp và hành động xử lý.

5\. Thử đăng nhập hợp lệ qua WAF.





\## 6. Minh chứng



Các ảnh chụp màn hình được lưu trong thư mục `img/`.





