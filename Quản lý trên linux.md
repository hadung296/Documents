# Quản lý user , group và  phân quyền trên linux 

**1.USER** 
<ul>
<li>User là người có thể truy nhập vào hệ thống :
<li>User bao gồm usename và password
<li>Có 2 loại user là : superuser và regularuser
<li>Mỗi user còn có một định danh riêng gọi là UID
<li>Định danh người dùng bình thường bất đàu từ giá trị 500
</ul>

**2.Group**
<ul>
<li>Group là tập hợp nhiều user lại.
<li>Mỗi user luôn là thành viên của một group.
<li>Khi tạo một user thì mặc định một group được tạo ra.
<li>Mỗi group còn có một định danh riêng gọi là GID.
<li>Định danh của group thường sử dụng giá trị bắt đầu từ 500.
</ul>

**3.Câu lệch tạo user và group**

** user** :
- tạo user
<ul>
<li> Cú pháp: #useradd [option] <username>
<li>-c “Thông tin người dùng”
<li>-d < Thư mục cá nhân >
<li>-m : Tạo thư mục cá nhân nếu chưa tồn tại
<li>-g < nhóm của người dùng >
</ul>
Ví dụ: #useradd –c “HMD” –g server 
- Thay đổi thông tin người dùng  : cú pháp usermod [option] < username >
- Xóa người dùng : userdel [option] < username >
- Khóa người dùng : passwd -l < username > 
- Mở khóa : passwd -u < username > 
- xem thông tin : id <username >

**  group **
- Tạo GR : groupadd < group name >
- Xóa GR : groupdel < group name >
- Xem thông tin : id <group name >
**Quyền hạn**

Trong Linux có 3 dạng đối tượng :
- Owner (người sở hữu).
- Group owner (nhóm sở hữu).
-	Other users (những người khác).
Các quyền hạn :
-	Read – r – 4  : cho phép đọc nội dung.
-	Write – w – 2  : dùng để tạo, thay đổi hay xóa.
-	Execute – x – 1  : thực thi chương trình.
**Các lệnh liên quan đến quyền hạn**
-	Lệnh Chmod : dùng để cấp quyền hạn.
Cú pháp : #chmod  <specification> <file>
Ví dụ: #chmod 644 baitap.txt   //cấp quyền cho owner có thể ghi các nhóm các chỉ có quyền đọc với file taptin.txt
-	Lệnh Chown : dùng thay đổi người sở hữu.
 Cú pháp : #chown  <owner>  <filename>
-	Lệnh Chgrp : dùng thay đổi nhóm sở hữu.
Cú pháp : #chgrp  <group>  <filename>

## Câu lêh tao, sửa , xóa file và foder trên Linux 
- ls: liệt kê tất cả các tập tin có thể nhìn thấy trong thư mục hiện hành.
- cd: Thay đổi thư mục.
- mkdir: Tạo thư mục mới.
- rmkdir : xóa thư mục 
- pwd: Xem đường dẫn của thư mục hiện hành.
- touch : tạo file 
- cp : copy 
- mv : di chuyển 
- rm : xóa file 
