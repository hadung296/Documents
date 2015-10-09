# Update
- Lệnh update cho chúng ta cập nhập các package . Câu lệnh trên sẽ cập nhập tất cả các package từ các repository 

# Upgrade vs Dist-Upgrade
- Thông thường các phần mềm mã nguồn mở thường được nâng cấp nhiều lần và thường xuyên có các bản cái tiến . Upgrade sẽ cho chúng
ta biết các package nào cần được cập nhập và tao có thể xác nhận lại những câp nhập đó . 
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

# Apache 

**1.Về apache**
- Apache nó cũng là 1 phần mềm cài đặt trên máy chủ để làm webserver.
- Apache hỗ trợ đắc lực trong http server . hỗ trợ nhiều loại ngôn ngữ phổ biến  Perl, Python, Tcl, và PHP .
- Apache có 3 chế độ hoạt động khác nhau : winnnt , prefork và worker 

**2. Cài đặt** 
