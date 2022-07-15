# Giao thức Secure Shell (SSH)

SSH là một giao thức mạng được mã hóa bảo mật, nó tạo ra kết nối bảo mật (tạo ra một đường hầm tách biệt với với cách dịch vụ khác để duy trì kết nối riêng tư giữa máy trạm và máy chủ) trên một mạng lưới không bảo mật. SSH cũng được hiểu như ứng dụng dùng để kết nối đăng nhập vào một hệ thống máy tính bởi người dùng.
![Image](https://raw.githubusercontent.com/xuanthulabnet/learn-ssh/master/imgs/ssh-01.png)


Giao thức SSH được dùng ở rất nhiều nền tảng từ Linux, macOs, Windows với các mục đích như:

  -Đăng nhập vào shell của máy tính từ xa (máy chủ)
  -Thi hành lệnh trên máy kết nối
  -Thiết lập tự động đăng nhập vào server
  -Truyền tải file an toàn
  -Gắn một thư mục ở máy từ xa (máy chủ) vào máy client
...


## Điều kiện và cách thức sử dụng SSH

Để sử dụng kết nối SSH, bạn phải được cung cấp một dịch vụ SSH từ máy Remote (từ xa, server), sau đó ở máy Client (local) sử dụng các chương trình SSH Client để kết nối đến máy remote và thực hiện các tác vụ tùy nhu cầu.

**Máy chủ dịch vụ SSH** là máy tại đó chạy một SSH Server, nó cung cập dịch vụ kết nối SSH đến nó, thông qua xác thực tài khoản user/pass hoặc xác thực bằng public/private key
Nếu đã được cung cấp tài khoản kết nối đến SSH Server, bạn chỉ việc sử dụng các Client SSH phù hợp để kết nối
Nếu muốn cài đặt và cấu hình một máy chủ SSH Server thì có thể sử dụng OpenSSH cho các máy chủ Linux hoặc phiên bản cho Windows tại OpenSSH - Windows

**SSH Client** là các chương trình chạy ở máy trạm (local) có chức năng kết nối đến SSH Server. Bản thân OpenSSH cũng là Client để kết nối - nên ở máy trạm ta sẽ tập trung vào sử dụng OpenSSH Client để thực hành, ngoài ra còn nhiều SSH Client khác, như Putty chạy trên Windows. Khi kết nối có thể tùy cấu hình từ OpenSSH Server có thể xác thực bằng cách nhập username/password hoặc bằng cặp file public/private key.

_Đối với Windows cũng đã hỗ trợ OpenSSH như là một gói phân phối cùng hệ điều hành, thông tin của Microsoft nó tích hợp sẵn trong Windows (từ năm 2018 - hoặc có thể cài thêm), điều này giúp cho việc sử dụng ngay SSH trên Windows 10, hoặc Server 2018 về sau mà không phải cài đặt thêm gì_


## Cấu hình máy chủ SSH trên Ubuntu
### Bước 1: Cài đặt các pakage bắt buộc
Cài đặt SSH Server được cung cấp bởi component openssh-server từ OpenSSH
```markdown
sudo apt install openssh-server
```
![image](https://user-images.githubusercontent.com/48356049/179161956-463fa81c-3bc8-4992-bf09-fef7f2e2efbc.png)
## Bước 2: Kiểm tra trạng thái của server
Khi quá trình tải xuống và cài đặt gói hoàn tất, dịch vụ SSH sẽ chạy, nhưng để chắc chắn, chúng ta cần kiểm tra trạng thái nó bằng
```markdown
service ssh status
```
hoặc
```markdown
sudo systemctl status ssh
```
Nếu kết quả như trong hình, dịch vụ đã được active
![image](https://user-images.githubusercontent.com/48356049/179162314-f1dc460a-1f49-429d-907e-9d3ae538758b.png)
Nếu dịch không chạy, phải kích hoạt bằng lệnh sau
```markdown
sudo systemctl enable --now ssh
```
### Bước 3: Cho phép SSH thông qua tường lửa (firewall)
Để cấu hình UFW sao cho nó cho phép truy cập mong muốn, bạn cần chạy lệnh sau:
```markdown
sudo ufw allow ssh
```
Ngoài ra, có thể dùng lệnh này để mở cổng cụ thể:
```markdown
sudo ufw allow [số cổng]/tcp
```
Có thể kiểm tra trạng thái của UFW đang chạy bằng lệnh:
```markdown
sudo ufw status
```
## Kết nối remote system
Cài đặt openssh-client bằng câu lệnh
```markdown
sudo apt install openssh-client
```
Để kết nối với ssh server, bạn cần biết địa chỉ IP của máy tính và sử dụng sshlệnh, như sau:
```markdown
ssh username@address
```
Kiểm tra địa chỉ IP của server bằng lệnh:
```markdown
ip a
```
![image](https://user-images.githubusercontent.com/48356049/179164157-71d07235-cb2f-4af7-a8f2-4fea366aed97.png)</br>
_Sử dụng "ip a" để tìm địa chỉ IP_
Lần đầu tiên bạn kết nối với máy chủ SSH, nó sẽ yêu cầu quyền thêm máy chủ. Nhập yes và nhấn Enter để tiếp tục.
![image](https://user-images.githubusercontent.com/48356049/179164290-6b8418fa-6f55-4b56-bd95-2f9b1ceeaa6c.png)</br>
_Lần đầu tiên kết nối với máy chủ_
Ngay lập tức SSH cho bạn biết rằng máy chủ đã được thêm vĩnh viễn và sau đó yêu cầu nhập mật khẩu được gán cho username. Nhập mật khẩu và nhấn Enter một lần nữa.
![image](https://user-images.githubusercontent.com/48356049/179164475-b16af5b9-a2d8-4694-9d32-0d87d5d5dadf.png)</br>
_Đã thêm máy chủ lưu trữ, bây giờ hãy nhập mật khẩu_
Cuối cùng, bạn đã đăng nhập thành công vào Ubuntu Remote System của mình
## Đóng kết nối SSH
Để đóng kết nối, bạn chỉ cần nhập **exit** và nó sẽ đóng ngay lập tức mà không cần yêu cầu xác nhận.
![image](https://user-images.githubusercontent.com/48356049/179166395-113cc559-a7f9-4e4e-9712-7ec718136584.png)
</br>
</br>
</br>
