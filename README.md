# Các nguyên tắc cơ bản của EC2
## Amazon EC2
- EC2 là một trong những dịch vụ phổ biến nhất của AWS
- EC2 = Elastic Compute Cloud là một dịch vụ cơ sở hạ tầng
- Gồm các tính năng:
    - **Cho thuê** máy áo (EC2)
    - **Lưu trữ** dữ liệu trên thiết bị ảo (EBS)
    - Phân phối tải trên các máy (ELB)
    - Chia tỷ lệ các dịch vụ bằng cách sử dụng nhóm tự động mở rộng quy mô (ASG)
- Biết EC2 là điều cơ bản để hiểu cách hoạt động của Clound
## Tùy chỉnh và cấu hình EC2
- HDH: Windows, Linux, MacOS
- Bao nhiêu CPU
- Bao nhiêu RAM
- Bộ nhớ bao nhiêu
    - Gắn mạng (EBS & EFS) 
    - Phần cứng
- Card mạng (tốc độ, Public IP addr)
- Firwall rules:
- Boostrap script (cấu hình lần đầu truy cập): EC2 User Data
## EC2 User Data
- Boostarp vào instance bằng cách sử dụng EC2 User Data script
- Boostarpping nghĩa là khởi chạy các lệnh khi máy khởi động
- Script đó chỉ run 1 lần khi instance khởi động lần đầu
