# Các nguyên tắc cơ bản của EC2
## Amazon EC2
- EC2 là một trong những dịch vụ phổ biến nhất của AWS
- EC2 = Elastic Compute Cloud là một dịch vụ cơ sở hạ tầng
- Đây là một dịch vụ web nơi người đăng ký AWS có thể yêu cầu và cung cấp máy chủ tính toán trong đám mây AWS.
- Gồm các tính năng:
    - **Cho thuê** máy áo (EC2)
    - **Lưu trữ** dữ liệu trên thiết bị ảo (EBS)
    - Phân phối tải trên các máy (ELB)
    - Chia tỷ lệ các dịch vụ bằng cách sử dụng nhóm tự động mở rộng quy mô (ASG)
- Biết EC2 là điều cơ bản để hiểu cách hoạt động của Cloud
## Tùy chỉnh và cấu hình EC2
- HDH: Windows, Linux, MacOS
- Bao nhiêu CPU
- Bao nhiêu RAM
- Bộ nhớ bao nhiêu
    - Gắn mạng (EBS & EFS) 
    - Phần cứng (EC2 Instance Store)
- Card mạng (tốc độ, Public IP addr)
- Firwall rules: security group
- Boostrap script (cấu hình lần đầu truy cập): EC2 User Data
## EC2 User Data
- Boostarpping nghĩa là khởi chạy các lệnh khi máy khởi động
- Boostarp vào instance bằng cách sử dụng EC2 User Data script (_Một EC2 Instance chính là một máy chủ ảo trong thuật ngữ dịch vụ Web của Amazon_)
- Script đó chỉ run 1 lần khi instance khởi động lần đầu
- EC2 User Data được sử dụng để tự động hóa các tác vụ khởi động như:
    - Cài đặt bản cập nhật
    - Cài đặt phần mềm
    - Tải xuống các tệp thông thường từ internet
    - Bất cứ điều gì bạn có thể nghĩ ra
- EC2 User Data Script chạy với root user
## Cách tạo một EC2 Instance với EC2 User Data
- B1: Truy cập vào EC2
![Ảnh tìm kiếm dịch vụ EC2](https://user-images.githubusercontent.com/48356049/198322313-c2677bd4-f21e-4c77-8432-d35b908daa97.png)

    Dưới đây là giao diện làm việc của EC2
![image](https://user-images.githubusercontent.com/48356049/198322984-7427864d-9075-4e37-a14d-11d8062c3198.png)

- B2: Truy cập vào instance

Sau khi chọn mục Instance trên menu thì ta có giao diện làm việc như sau:
![image](https://user-images.githubusercontent.com/48356049/198323944-b5fc71a6-e651-4787-8b2c-01c5b5c9648e.png)

- B3: Chọn Launch Instance và thực hiện các bước sau:
    - Điền tên instance muốn tạo
    ![image](https://user-images.githubusercontent.com/48356049/198327185-19f4d62b-9c29-49b3-b7e2-14644be2b52d.png)

    - Lựa chọn AMI
        - Bạn sẽ được yêu cầu chọn một AMI theo lựa chọn của bạn. (AMI là một hình ảnh -Amazon Machine Image. Nó là một mẫu cơ bản của nền tảng Hệ điều hành mà bạn có thể sử dụng làm cơ sở để tạo Instance của mình). Khi bạn khởi chạy một EC2 Instance từ AMI ưa thích của mình, Instance đó sẽ tự động được khởi động với HĐH mong muốn. 
        - Ở đây tôi đang chọn Amazon Linux (64 bit) AMI mặc định.
    
    ![image](https://user-images.githubusercontent.com/48356049/198327546-ee3a939b-4058-4544-968c-5d0ec447bf47.png)
        
    ![image](https://user-images.githubusercontent.com/48356049/198327927-2221aba7-6e5a-44ff-bb71-d3432effc512.png)
    
    - Lựa chọn Instance
    
    Ở bước này, chúng ta cần chọn loại Instance dựa trên nhu cầu của mình

        - Ở đây ta chọn loại instance là: t2.micro, đó là máy chủ 1vCPU và 1GB bộ nhớ do AWS cung cấp.
        - Nhấp vào "Configure Instance Details" để biết thêm cấu hình
        
    ![image](https://user-images.githubusercontent.com/48356049/198329809-8f4e9d02-9467-4c11-b63b-4fa523c7e56c.png)
    
    - Tạo key pair
    
    ![image](https://user-images.githubusercontent.com/48356049/198332172-2a28cbb7-550a-4761-ab28-8894c928f391.png)
    
        - Nhập tên key pair
        - Đối với SSH Client là windows 10 trở lên thì chọn .pem, còn lại chọn .ppk
        - Sau khi nhấn "Create key pair thì có 1 key pair được tạo thành và tự động download xuống
    
    ![image](https://user-images.githubusercontent.com/48356049/198332268-6c4f25c7-cf82-495c-96e0-55b46c45b082.png)

    
    -  Cấu hình network
    
    ![image](https://user-images.githubusercontent.com/48356049/198330375-30314891-b989-48f3-afcf-487094a6b7f6.png)
    
    - Cấu hình storage
    
    ![image](https://user-images.githubusercontent.com/48356049/198331119-141b1deb-a174-41e9-a25b-f781d104544d.png)

    - Avanced setting
    
        - Nhập User Data script 
    
    ![image](https://user-images.githubusercontent.com/48356049/198331899-2b68f797-1544-48ee-ad40-96184dbdcad6.png)

- B4: Chọn Launch Instance để hoàn thành việc tạo Instance

![image](https://user-images.githubusercontent.com/48356049/198333239-773deefc-60a9-43c1-bb89-b90a6d3e7528.png)

- B5: Chọn View all instance
- B6: Khi instance đã ở trạng thái Running ==> chọn instance để xem thông tin của nó

![image](https://user-images.githubusercontent.com/48356049/198334008-b3ff0d70-659c-42e4-8c43-419d47d7a374.png)

- B7: Copy Public address và chọn open address

![image](https://user-images.githubusercontent.com/48356049/198334248-899dbc49-e607-493d-b041-c3a249be77f3.png)

- B8: Paste địa chỉ vừa copy vào trình duyệt và enter để xem kết quả

![image](https://user-images.githubusercontent.com/48356049/198334661-ba24ffe4-39fb-4cc3-92a4-a4dabe034661.png)









