# Update
- Lệnh update cho chúng ta cập nhập các package . Cập nhập các packege cho file sources trong hệ thống và cập nhập các gói mới để nâng cấp các phiên bản đã cũ 

# Upgrade vs Dist-Upgrade
- Thông thường các phần mềm mã nguồn mở thường được nâng cấp nhiều lần và thường xuyên có các bản cái tiến . Upgrade sẽ cho chúng ta biết các package nào cần được cập nhập và tao có thể xác nhận lại những câp nhập đó . 
- Upgrade sẽ thay thế hoàn toàn phiên bản cũ bằng phiên bản mới
- Tuy nhiên có 1 vài trường hợp , 1 số phần mềm lại yêu cầu gói cài đăt trước đó vì vậy ta s dung dist-upgrade
- Lệnh này thực sự hữu ích nếu bạn không chắc rằng việc cập nhật này có ảnh hưởng đến các thành phần khác trong hệ thống hay không

# Cài đặt phần mềm trên các distro khác nhau 
- Distro khác nhau là ở phần quản lý gói . Các gói cài đặt có phần mở rộng khác nhau và có các cách cài đặt trên các distro khac
nhau lí do linux là phần mềm mã nguồn mở và phần biên dịch trên mỗi distro la không giống nhau. Trên các distro khác nhau thì đường dẫn cũng khác nhau. 

**1.Cài đặt trên redhat- centos**

- Gói RPM
<ul>
<li>Bản thân các gói RPM không chứa phần cài đặt mà nó chỉ chứa các thông tin cài đặt như đường dẫn tới file ... Cách đơn giản để cài 1 gói RPM là dùng câu lệnh : rpm -i "tên gói".rpm 
<li>khi muốn gỡ gói cài đặt rpm nào đó : rpm -e  "tên gói".rpm 
<li>Lấy thông tin từ gói : rpm -qpi  "tên gói".rpm 
</ul>
- Các gói tin nén TAR:
<ul>
<li> Bung nén dùng: tar  "tên gói".tar.gr
<li> Sau đó dùng make và make install để cài đặt gói 
</ul>
- Ở centos ta còn có lệnh yum 
<ul>
<li>Để cài đặt ta dung câu lệnh : yum install  "tên gói" 
<li>Hay tìm kiếm các gói : yum seach  "tên gói"
</ul>

**2.Cài đạt phần mềm trên ubuntu**

- Cài đặt các file .deb  rất dễ, bạn chỉ cần click đúp vào file và trình cài đặt phần mềm trên hệ thống tự mở, click “Install Package” và chờ quá trình cài đặt hoàn tất. Cái này chắc là được biên dịch mã nguồn sẵn :3 
- Đối với các file rpm chúng ta có thể cài thêm công cụ alien để dịch từ rpm sang deb .  Mở Terminal lên, gõ vào sudo apt-get install alien . (ví dụ bạn tải file đó về desktop thì CD desktop và sudo alien -k "tên gói" để chuyển về deb .
- Các gói nén 
<ul>
<li>Đối với các gói nén các bạn cần lệnh : tar "tên gói"
<li> ./configure  để kiểm tra thông tin cài đặt như các gói GCC ...( các gói môi trường :3)
<li>sodu make và sudo make install để cài gói 
</ul>

# Cấu hình card mạng cho ubuntu

- Để cấu hình cho card mạng ubuntu ta sửa và thêm card mạng cho file interfaces theo đường dẫn etc/network/interfaces

![Imgur](http://i.imgur.com/QditsOL.png)

- Sau đó lưu lại thông tin và restart lại card mạng 

# Apache 

**1.Về apache**
- Apache nó cũng là 1 phần mềm cài đặt trên máy chủ để làm webserver.
- Apache hỗ trợ đắc lực trong http server . hỗ trợ nhiều loại ngôn ngữ phổ biến  Perl, Python, Tcl, và PHP .
- Apache có 3 chế độ hoạt động khác nhau : winnnt , prefork và worker 

**2. Cài đặt apache** 

- Chuyển sang quyền root với lệnh sudo su 
![Imgur](http://i.imgur.com/DdqtfM2.png)

- apt-get update 
![Imgur](http://i.imgur.com/OOH2Zkp.png)

- cài đặt apache : sudo apt-get apache2 và đợi quá trình cài đặt hoàn tất .
- Hoàn tất cài đặt và kiểm tra thông server 

![Imgur](http://i.imgur.com/zIoGD4N.png)

**Cấu hình apache **

/var/www : Thư mục mặc định chứa website

/etc/apache2/apache2.conf : File cấu hình Apache2

/etc/apache2/mods-enabled : Thư mục chứa các module của Apache module (các module đang hoạt động

/etc/apache2/sites-enabled : Thư mục chứa các cài đặt định danh cho các website (Virtual Host)

/etc/apache2/conf.d : Các cấu hình mở rộng cho Apache.

Sau khi cài đặt Apache, ứng dụng sẽ được thêm vào danh sách init.d của hệ thống, do đó có thể tự khởi động cùng với hệ điều hành. Sử dụng những lệnh sau để khởi động, kích hoạt và ngừng hoạt động của Apache:

- sudo /etc/init.d/apache2 start #chạy apache
- sudo /etc/init.d/apache2 stop #dừng apache
- sudo /etc/init.d/apache2 restart #khởi động lại apache
- Nếu không muốn Apache tự khởi động cùng hệ thống, gõ lệnh sau:

sudo update-rc.d -f apache2 remove

Còn nếu muốn làm ngược lại quá trình trên (khởi động cùng hệ thống) thì sử dụng lệnh:

sudo update-rc.d apache2 defaults

