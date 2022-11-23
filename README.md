# EC2 Instance Storage
## EBS 
- Amazon Elastic Block Store (EBS) là một dịch vụ lưu trữ dạng block dễ sử dụng và hiệu năng cao, được thiết kế để sử dụng với Amazon Elastic Compute Cloud (EC2) cho các khối lượng công việc đòi hỏi tốc độ giao dịch và thông lượng cao ở mọi quy mô.
### Lợi thế của EBS
- Có độ trễ thấp (low-latency performance): Bằng cách sử dụng SSD EBS, nó cung cấp hiệu suất I/O đáng tin cậy, tối ưu nhu cầu khối lượng công việc và dung lượng lưu trữ.
- EBS đảm bảo tất cả dữ liệu của bạn được bảo vệ. Vì nó cho phép các instances duy trì dữ liệu, thông qua Snapshot, ngay cả khi instances đó có bị terminate đi nữa.
- Khả năng lưu trữ an toàn và khả dụng cao: EBS volumes cung cấp dung lượng dự phòng trong AZ, kiểm soát truy cập và mã hóa tăng cường bảo mật.
- Thay đổi vị trí địa lý: Với EBS, bạn có thể duplicate snapshot qua khắp các regions, có thể đặt tài nguyên và dữ liệu ở nhiều vị trí khác nhau. Phục vụ cho khôi phục data sau thảm họa, ...
- EBS có thể nhanh chóng scale up or down volumes, đảm bảo bạn sẽ nhận được hiệu suất và dung lượng phù hợp cho các nhu cầu đang thay đổi.
### Sử dụng EBS như thế nào
- 1 EBS muốn được sử dụng, bắt buộc phải gắn nó vào 1 EC2 instance.
- EBS cũng thuộc về 1 AZ cụ thể. Ví dụ EBS A thuộc AZ "abc", nhưng instance B thuộc AZ "cde" thì không thể nào gắn EBS A cho instance B được.
- 1 EBS chỉ có thể attach tới 1 instance tại 1 thời điểm.

![image](https://user-images.githubusercontent.com/48356049/203505704-e0255dff-4384-4e59-8e70-09cc01c68993.png)

### Note
Đơn giản, hãy xem EBS như 1 USB có gắn mạng
Free tier: 30GB free mỗi tháng cho option General Purpose SSD (gp2) hoặc Magnetic
