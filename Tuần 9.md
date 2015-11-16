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

![Imgur](http://i.imgur.com/ylugXE3.png)

Như vậy ta có thể ssh vào ubuntu server từ putty !!

**Tạo SSH Key**

*Trên win*

- Tải SSH Key tại : http://the.earth.li/~sgtatham/putty/0.66/x86/puttygen.exe
- Nhấn nút ‘Generate’

![Imgur](http://i.imgur.com/XZD7OMT.png)

- Sau khi key đã được generate, nhấn ‘Save Private Key’. Đảm bảo bạn lưu key file ở một nơi an toàn.

![Imgur](http://i.imgur.com/fam67aw.png)

*Trên máy ubuntu server*

- Chạy ssh-keygen -t rsa
- Nhấn Enter khi được hỏi nơi lưu key file (mặc định /root/.ssh/id_rsa)
- Nhập passphrase nếu cần
- Tiếp theo, ta load Puttygen .Và chạy nó ở windown client.Giao diện của Puttygen xuất hiện như hình sau.

![Imgur](http://i.imgur.com/XZD7OMT.png)

![Imgur](http://i.imgur.com/fam67aw.png)

- Mở PuTTY và chuyển tới trường Auth và chọn file .ppk mà ta đã lưu ở trên.

![Imgur](http://i.imgur.com/msRxpUt.png)

- Tiếp theo, ta quay lại trường Session và nhập vào IP của ssh server.Nhập vào user mà ta đã cấu hình chứng thực bằng Keys Authentication.

![Imgur](http://i.imgur.com/aQW5871.png)

.........

![Imgur](http://i.imgur.com/u1ZGm4j.png)





