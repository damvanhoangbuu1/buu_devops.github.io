# EC2
## SSH Overview
### SSH Summary Table
![image](https://user-images.githubusercontent.com/48356049/200762852-09f19b19-25fc-4686-a872-a3f5bb4be366.png)
### EC2 Instance Roles
![image](https://user-images.githubusercontent.com/48356049/203492764-026ec090-389b-4d4a-a65f-75771bbcbfe5.png)

Nguyên tắc là không bao giờ đăng nhập trực tiếp (bảo mật) --> sử dụng user role để đăng nhập

- Cách add Roles vào EC2 Instance:
  B1. Chọn EC2 Instance cần thêm Roles --> Action --> Security --> Modify IAM Roles --> Có giao diện như hình dưới
  
![image](https://user-images.githubusercontent.com/48356049/203493764-27f444a2-078b-4ce4-8a96-94dd7eb7a0c3.png)

  B2. Chọn IAM Roles được tạo sẵn có trong khung đỏ 
  
  ![image](https://user-images.githubusercontent.com/48356049/203494086-de72c386-879f-48c3-b9bf-4a867ed43cc8.png)

* Lưu ý: IAM Roles EC2 Instance cần có Policy AMReadOnlyAccess

