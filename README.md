## How to choose an AWS Region?
Các yếu tố ảnh hưởng đến việc chọn AWS Region:
- **Tuân thủ** các yêu cầu pháp lý và quản lý dữ liệu: dữ liệu không bao giờ rời khỏi một khu vực mà không có sự cho phép rõ ràng của bạn
- **Gần** khách hàng: giảm độ trễ
- Các **dịch vụ khả dụng** trong Region: các dịch vụ mới và tính năng mới không có sẵn ở mọi Region
- **Giá cả**: giá cả khác nhau giữa các khu vực và minh bạch trong trang giá dịch vụ

## AWS Availability Zones
Mỗi khu vực có nhiều khu vực khả dụng
(thường là 3, tối thiểu là 2, tối đa là 6). Thí dụ:
- ap-southeast-2a
- ap-southeast-2b
- ap-southeast-2c

![Hình minh họa](https://user-images.githubusercontent.com/48356049/193997475-63fe5bf2-e9b6-4c9e-9c54-24bfea3d0d39.png)


Mỗi vùng khả dụng (AZ) là một hoặc nhiều trung tâm dữ liệu rời rạc có nguồn, mạng và kết nối dự phòng

Chúng tách biệt với nhau, để chúng bị cách ly khỏi thảm họa

Chúng được kết nối với băng thông cao, mạng độ trễ cực thấp

_**Kiểm da dịch vụ khả dụng trong Region**_

Region Table: https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services
