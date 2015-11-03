#Một số câu lệnh đơn giản với SQL 

**set quyền user **

  Hiển thị toàn bộ users:
mysql> SELECT * FROM mysql.user;

Xóa null user:
mysql> DELETE FROM mysql.user WHERE user = ' ';

Xóa tất cả user mà không phải root:
mysql> DELETE FROM mysql.user WHERE NOT (host="localhost" AND user="root");

Đổi tên tài khoản root (giúp bảo mật):
mysql> UPDATE mysql.user SET user="mydbadmin" WHERE user="root";

Gán full quyền cho một user mới:
mysql> GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;

Phân quyền chi tiết cho một user mới:
mysql> GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass';

Gán full quyền cho một user mới trên một database nhất định:
mysql> GRANT ALL PRIVILEGES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;

Thay đổi mật khẩu user:
mysql> UPDATE mysql.user SET password=PASSWORD("newpass") WHERE User='username';

Xóa user:
mysql> DELETE FROM mysql.user WHERE user="username";
