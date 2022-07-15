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

*Máy chủ dịch vụ SSH* là máy tại đó chạy một SSH Server, nó cung cập dịch vụ kết nối SSH đến nó, thông qua xác thực tài khoản user/pass hoặc xác thực bằng public/private key
Nếu đã được cung cấp tài khoản kết nối đến SSH Server, bạn chỉ việc sử dụng các Client SSH phù hợp để kết nối
Nếu muốn cài đặt và cấu hình một máy chủ SSH Server thì có thể sử dụng OpenSSH cho các máy chủ Linux hoặc phiên bản cho Windows tại OpenSSH - Windows

*SSH Client* là các chương trình chạy ở máy trạm (local) có chức năng kết nối đến SSH Server. Bản thân OpenSSH cũng là Client để kết nối - nên ở máy trạm ta sẽ tập trung vào sử dụng OpenSSH Client để thực hành, ngoài ra còn nhiều SSH Client khác, như Putty chạy trên Windows. Khi kết nối có thể tùy cấu hình từ OpenSSH Server có thể xác thực bằng cách nhập username/password hoặc bằng cặp file public/private key.

Đối với Windows cũng đã hỗ trợ OpenSSH như là một gói phân phối cùng hệ điều hành, thông tin của Microsoft nó tích hợp sẵn trong Windows (từ năm 2018 - hoặc có thể cài thêm), điều này giúp cho việc sử dụng ngay SSH trên Windows 10, hoặc Server 2018 về sau mà không phải cài đặt thêm gì

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/damvanhoangbuu1/buu_devops.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
