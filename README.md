## Giao thức Secure Shell (SSH)

SSH là một giao thức mạng được mã hóa bảo mật, nó tạo ra kết nối bảo mật (tạo ra một đường hầm tách biệt với với cách dịch vụ khác để duy trì kết nối riêng tư giữa máy trạm và máy chủ) trên một mạng lưới không bảo mật. SSH cũng được hiểu như ứng dụng dùng để kết nối đăng nhập vào một hệ thống máy tính bởi người dùng.
![Image](https://raw.githubusercontent.com/xuanthulabnet/learn-ssh/master/imgs/ssh-01.png)


Giao thức SSH được dùng ở rất nhiều nền tảng từ Linux, macOs, Windows với các mục đích như:

  -Đăng nhập vào shell của máy tính từ xa (máy chủ)
  -Thi hành lệnh trên máy kết nối
  -Thiết lập tự động đăng nhập vào server
  -Truyền tải file an toàn
  -Gắn một thư mục ở máy từ xa (máy chủ) vào máy client
...


### Điều kiện và cách thức sử dụng SSH

Để sử dụng kết nối SSH, bạn phải được cung cấp một dịch vụ SSH từ máy Remote (từ xa, server), sau đó ở máy Client (local) sử dụng các chương trình SSH Client để kết nối đến máy remote và thực hiện các tác vụ tùy nhu cầu.

**Máy chủ dịch vụ SSH** là máy tại đó chạy một SSH Server, nó cung cập dịch vụ kết nối SSH đến nó, thông qua xác thực tài khoản user/pass hoặc xác thực bằng public/private key
Nếu đã được cung cấp tài khoản kết nối đến SSH Server, bạn chỉ việc sử dụng các Client SSH phù hợp để kết nối
Nếu muốn cài đặt và cấu hình một máy chủ SSH Server thì có thể sử dụng OpenSSH cho các máy chủ Linux hoặc phiên bản cho Windows tại OpenSSH - Windows

**SSH Client** là các chương trình chạy ở máy trạm (local) có chức năng kết nối đến SSH Server. Bản thân OpenSSH cũng là Client để kết nối - nên ở máy trạm ta sẽ tập trung vào sử dụng OpenSSH Client để thực hành, ngoài ra còn nhiều SSH Client khác, như Putty chạy trên Windows. Khi kết nối có thể tùy cấu hình từ OpenSSH Server có thể xác thực bằng cách nhập username/password hoặc bằng cặp file public/private key.

_Đối với Windows cũng đã hỗ trợ OpenSSH như là một gói phân phối cùng hệ điều hành, thông tin của Microsoft nó tích hợp sẵn trong Windows (từ năm 2018 - hoặc có thể cài thêm), điều này giúp cho việc sử dụng ngay SSH trên Windows 10, hoặc Server 2018 về sau mà không phải cài đặt thêm gì_


