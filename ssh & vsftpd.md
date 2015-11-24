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

#FTP

  Tiêu chuẩn File Transfer Protocol (FTP) – Giao thức truyền tệp tin
  
  Mục đích của FTP là: Đẩy mạnh chia sẻ tệp tin (các chương trình máy tính và/hoặc dữ liệu); Khuyến khích sử dụng máy tính truy cập gián tiếp từ xa vào các tệp tin; Giúp người sử dụng dễ dàng truy cập vào các hệ thống lưu trữ khác nhau; Truyền dữ liệu một cách đáng tin cậy và hiệu quả cao.
  
  FTP được xây dựng trên mô hình máy khách - máy chủ (client - server), trong đó, máy chủ FTP cài đặt phần mềm cung cấp dịch vụ FTP và lắng nghe yêu cầu về dịch vụ FTP của các máy tính trên mạng, máy khách cài đặt phần mềm FTP dành cho người sử dụng khởi tạo một liên kết với máy chủ. Máy khách có thể thực hiện một số chức năng như tải lên/tải xuống tệp tin từ máy chủ, đổi tên hoặc xóa tệp tin khi đã kết nối với máy chủ FTP.
  
  *Đặc điểm của FTP*

FTP truyền tệp tin theo cách không an toàn, có nghĩa là dữ liệu được truyền đi mà không được mã hóa. Để giải quyết vấn đề này, IETF khuyến nghị sử dụng giao thức SFTP (Secure File Transfer Protocol) được xây dựng dựa trên nền giao thức SSH hoặc giao thức FTPS (FTP over SSL). FTPS là phần mở rộng của FTP bao gồm chức năng mã hóa dữ liệu của SSL hoặc TLS.  
  
  *Mô hình*

![Imgur](http://i.imgur.com/MQ1ayKk.jpg)

#Cấu hình FTP cho ubuntu server , ftp site, phân quyền người dùng

Vsftpd là một trong những chương trình ftp server được sử dụng rộng rãi trên Linux server, sử dụng vsftpd gần như chúng ta có thể yên tâm với các lỗ hổng về bảo mật với ftp server.

*Cài đặt *
  
- Chuyển về quyền root : sudo -i 
- chạy lệnh apt-get install vsftpd 

*Cấu hình*

Chúng ta sẽ cấu hình cho vsftpd ở file /etc/vsftpd.conf

vi /etc/vsftpd.conf

1. Việc đầu tiên cần làm là tắt quyền truy cập của anonymous user bằng cách thay đổi anonymous_enable từ yes sang no

anonymous_enable=NO

2. Thứ 2 cần cấp quyền tạo và ghi thư mục

bỏ comment trước local_enable và chuyển giá trị từ NO sang YES

local_enable=YES

write_enable=YES

- Cuối cùng bỏ comment chroot_local_user và chuyển NO sang YES. 

chroot_local_user=YES

- Tạo thư mục riêng cho user

mkdir /home/username/files

- Thay đổi quyền truy cập

chown root:root /home/username

- Việc còn lại là khởi động lại vsftpd

sudo service vsftpd restart

