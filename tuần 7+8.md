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

##So sánh giữa Wordpress và Joomla

**Joomla**

  Trước hết, liên quan đến Joomla, nó là một lựa chọn tốt nếu bạn quan tâm trong việc tạo ra một mạng hoặc một cộng đồng bao gồm các tính năng mạng nhóm như diễn đàn, tạp chí, hệ quản trị, ứng dụng nền web... Điều có được là do Joomla được thiết kế rất cơ bản để phục vụ các chức năng lớn và chặt chẽ. Nó rất dễ dàng để tạo ra một cấu trúc điều hướng thông qua trang web của bạn mà không cần phải html khi bạn hiểu được cách Joomla. Bạn có thể dễ dàng thiết lập ngày hết hạn bài viết, ví dụ, hoặc tên tác giả, ngày kích hoạt, và các cấu hình khác. Nói cách khác, bạn có rất nhiều quyền lực theo ý của bạn với Joomla, đặc biệt là trong phần trang quản trị trang web của bạn, nơi bạn có thể trở nên chóng mặt với các tùy chọn bạn đang trình bày. Do bộ tính năng phong phú có sẵn với Joomla, bạn có thể muốn xem xét một số hướng dẫn hoặc hướng dẫn sử dụng để giúp bạn bắt đầu.
 
  Mặt khác, nếu bạn quan tâm trong việc sửa đổi giao diện của trang web của bạn một chút, chẳng hạn như thông qua việc thay đổi logo của bạn hoặc một số màu sắc, nó là một quá trình đơn giản để làm, nhưng nếu bạn quan tâm đến việc đó nhiều hơn, bạn sẽ sớm khám phá ra rằng cấu trúc cơ bản của Joomla có thể phức tạp ngay cả đối với các nhà phát triển web dài dạn, không bao giờ nhớ cho người mới bắt đầu. Bạn luôn có thể phải trả tiền cho các template chuyên nghiệp, tuy nhiên, hoặc yêu cầu các nhà phát triển để thiết kế trang web của bạn cho bạn nếu bạn không quan tâm đến làm việc với các stylesheet. Như bạn có thể thấy, điểm mạnh và điểm yếu của Joomla nằm trong sự phức tạp của nó.

**Wordpress**

  WordPress, mặt khác, được thiết kế rất thân thiện với người dùng và làm việc như một hệ thống blog cơ bản. Tương tự như Joomla, bạn có thể cập nhật nó mà không cần bất kỳ kiến thức về html. Nó rất dễ dàng để tạo ra bài viết và các trang, và thông qua các plugin, bạn có thể thêm một số bộ tính năng và chức năng tương tự như Joomla. Tuy nhiên, đoạn mã sẽ đạt được tất cả các tiêu chuẩn web, mà sẽ làm cho trang web thân thiện hơn với Google.
 
  Bởi vì WordPress được thiết kế thân thiện với người sử dụng, nó sẽ đi kèm với một giao diện dễ hiểu. Nếu bạn quan tâm trong việc thích ứng giao diện của trang web của bạn, tuy nhiên, bạn sẽ cần phải có một số kiến thức về các ngôn ngữ phong cách được sử dụng, đó là CSS. Tương tự như Joomla, nếu bạn chọn một mẫu trông khá giống như những gì bạn muốn, bên cạnh một vài màu sắc và biểu tượng, sau đó bạn sẽ không có nhiều việc phải làm. Tuy nhiên, nếu bạn muốn có thêm nhiều tính năng hoặc một giao diện theo ý muón, sau đó bạn sẽ được tốt hơn việc thuê một nhà phát triển web, nếu bạn không muốn dành thời gian để lỗ chân lông thông qua các hướng dẫn và hướng dẫn sử dụng.
 
  Trong ngắn hạn, những lợi thế của WordPress nằm trong sự đơn giản của nó và khả năng thích ứng của nó trong sử dụng hoặc là một trang web thông thường hay một blog, hỗ trợ rất tốt cho SEO, trong khi những lợi thế của Joomla nằm trong khả năng tùy biến và mở rộng quy mô từ đơn giản đến phức tạp.
