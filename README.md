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

# IAM Section

## IAM: Users & Group

- IAM = Identity and Access Management, (là 1 dịch vụ toàn cầu)
- **Root user** được tạo theo mặc định, không được sử dụng hoặc chia sẻ
- **User** là những người trong tổ chức của bạn và có thể được nhóm lại
- **Group** chỉ chứa người dùng, không chứa các nhóm khác
- **User** không nhất thiết phải thuộc một **Group** và **User** có thể thuộc nhiều **Group**

![image](https://user-images.githubusercontent.com/48356049/194000693-08a391b0-c1d4-410a-9b3d-c6d8bc28b641.png)

## IAM: Permissions
- **User** hoặc **Group** có thể được chỉ định tài liệu JSON được gọi là chính sách
- Các chính sách này xác định quyền của **User**
- Trong AWS, bạn áp dụng nguyên tắc đặc quyền ít nhất: không cấp nhiều quyền hơn mức người dùng cần

![image](https://user-images.githubusercontent.com/48356049/194001296-79c435cb-aa73-46a5-9433-cd6ff31a5788.png)

## IAM Policies Structure
- Consists of
  - Version: phiên bản ngôn ngữ policy (chính sách), thường dùng “2012-10-17”
  - Id: số nhận dạng cho policy (tùy chọn)
  - Statement: one or more individual statements (required)
  
-  Statements consists of
    - Sid: an identifier for the statement (optional)
    - Effect: whether the statement allows or denies access  (Allow, Deny)
    - Principal: account/user/role to which this policy applied to
    - Action: list of actions this policy allows or denies
    - Resource: list of resources to which the actions applied to
    - Condition: conditions for when this policy is in effect (optional)

![image](https://user-images.githubusercontent.com/48356049/194013032-7e84d861-19de-4908-8672-a05c080c186e.png)

