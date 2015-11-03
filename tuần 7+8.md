#Một số câu lệnh đơn giản với SQL 

**set quyền user **

- Hiển thị toàn bộ users:   mysql> SELECT * FROM mysql.user;
- Xóa null user:      mysql> DELETE FROM mysql.user WHERE user = ' ';
- Xóa tất cả user mà không phải root:   mysql> DELETE FROM mysql.user WHERE NOT (host="localhost" AND user="root");
- Đổi tên tài khoản root (giúp bảo mật):  mysql> UPDATE mysql.user SET user="mydbadmin" WHERE user="root";
- Gán full quyền cho một user mới:  mysql> GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;
- Phân quyền chi tiết cho một user mới: mysql> GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass';
- Gán full quyền cho một user mới trên một database nhất định:  mysql> GRANT ALL PRIVILEGES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;
- Thay đổi mật khẩu user: mysql> UPDATE mysql.user SET password=PASSWORD("newpass") WHERE User='username';
- Xóa user:   mysql> DELETE FROM mysql.user WHERE user="username";

**tạo database, bảng cột, select**

*select*

SELECT "-----" FROM "-----"

*database* 

-Hiển thị toàn bộ databases:  mysql> SHOW DATABASES;
- Tạo database:   mysql> CREATE DATABASE mydatabase;
- Sử dụng một database:   mysql> USE mydatabase;
- Xóa một database:   mysql> DROP DATABASE mydatabase;
- Tối ưu database:
- All Databases: $ sudo mysqlcheck -o --all-databases -u root -p
- Single Database: $ sudo mysqlcheck -o db_schema_name -u root -p

*table*

- Hiển thị toàn bộ table: mysql> SHOW TABLES;
- Hiển thị dữ liệu của table:   mysql> SELECT * FROM tablename;
- Đổi tên table :    mysql> RENAME TABLE first TO second; hoặc mysql> ALTER TABLE mytable rename as mynewtable;
- Xóa table:    mysql> DROP TABLE mytable;

*cột và hàng*

- Hiển thị các column trong table:  mysql> DESC mytable; hoặc mysql> SHOW COLUMNS FROM mytable;
- Đổi tên column:   mysql> UPDATE mytable SET mycolumn="newinfo" WHERE mycolumn="oldinfo";
- Select dữ liệu:   mysql> SELECT * FROM mytable WHERE mycolumn='mydata' ORDER BY mycolumn2;
- Insert dữ liệu vào table:
mysql> INSERT INTO mytable VALUES('column1data','column2data','column3data','column4data','column5data','column6data','column7data','column8data','column9data');
- Xóa dữ liệu trong table:  mysql> DELETE FROM mytable WHERE mycolumn="mydata";
- Cập nhật dữ liệu trong table:
mysql> UPDATE mytable SET column1="mydata" WHERE column2="mydata";


