# Dùng putty để shh vào ubuntu server 

  SSH :SSH là một chương trình tương tác giữa máy chủ và máy khách có sử dụng cơ chế mã hoá đủ mạnh nhằm ngăn chặn các hiện tượng nghe trộm, đánh cắp thông tin trên đường truyền. Các chương trình trước đây: telnet, rlogin không sử dụng phương pháp mã hoá. Vì thế bất cứ ai cũng có thể nghe trộm thậm chí đọc được toàn bộ nội dung của phiên làm việc bằng cách sử dụng một số công cụ đơn giản. Sử dụng SSH là biện pháp hữu hiệu bảo mật dữ liệu trên đường truyền từ hệ thống này đến hệ thống khác.

**Cài đặt putty để ssh vào ubuntu server**

*Trên ubuntu server*

- Cài gói openssh-server với câu lệnh apt-get install openssh-server 
- Khởi động nó với lệnh : sudo /etc/init.d/shh start 
- Cấu hình shh : sudo vi /etc/shh/shhd_config

Sửa lại nội dung :

![Imgur](http://i.imgur.com/rXSVoZv.png)

- Lưu và khởi động lại : sudo /etc/init.d/shh start 

*Trên máy sử dụng win*

Tải putty http://the.earth.li/~sgtatham/putty/0.66/x86/putty.exe

Tại host name nhập IP của máy ubuntu server 

![Imgur](http://i.imgur.com/N6I8v4x.png)

Sau đó nhập user và passwd 

![Imgur](http://i.imgur.com/K3JcSfE.png)

[Imgur](http://i.imgur.com/ylugXE3.png)

Như vậy ta có thể ssh vào ubuntu server từ putty !!

**Tạo SSH Key**

*Trên win*

- Tải SSH Key tại : http://the.earth.li/~sgtatham/putty/0.66/x86/puttygen.exe
- Nhấn nút ‘Generate’

![Imgur](http://i.imgur.com/XZD7OMT.png)

- Sau khi key đã được generate, nhấn ‘Save Private Key’. Đảm bảo bạn lưu key file ở một nơi an toàn.

*Trên máy ubuntu server*






