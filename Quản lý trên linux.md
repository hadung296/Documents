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
- Tạo user :
<ul>
<li> Cú pháp: #useradd [option] <username>
<li>-c “Thông tin người dùng”
<li>-d < Thư mục cá nhân >
<li>-m : Tạo thư mục cá nhân nếu chưa tồn tại
<li>-g < nhóm của người dùng >
</ul>
Ví dụ: #useradd –c “HMD” –g server 
- Tạo group :
<ul>


