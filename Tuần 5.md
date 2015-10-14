# 1.Nguyên tắc sử lý của webserver 

![Imgur](http://i.imgur.com/ZK3Ib8H.png)

Khi  Web Server nhận 1 yêu cầu từ Web Browser, nó dẫn đến URL (ví dụ: http://www.actvn.edu.vn/)  thành một tập tin cục bộ trên 
máy Web Server
Máy chủ sau đó sẽ nạp tập tin này từ  đĩa và gởi tập tin đó qua mạng đến Web Browser của người dùng. 
Web Browservà Web Serversử dụng giao thức HTTPtrong quá trình trao đổi dữ liệu 

**cơ chế nhận kết nối** 

Với phiên bản đầu tiên, Web Serverhoạt động theo mô hình sau:

- Tiếp nhận các yêu cầu từ Web Browser.
- Trích nội dung từ đĩa .
- Chạy các chương trình CGI (Common Gateway Interface).
- Truyền dữ liệu ngược lại cho Client

Tuy vậy cách hoạt động của mô hình trên không hoàn toàn tương thích lẫn nhau. Một Web Server đơn giản phải theo các luật logic :

- Chấp nhận kết nối.
- Sinh ra các nội dung tĩnh hoặc động cho Browser.
- Đóng kết nối.
- Chấp nhận kết nối.
- Lập lại quá trình trên ...

Điều này sẽ chạy tốt đối với các Web Sites đơn giản, nhưng Serversẽ bắt đầu gặp phải vấn đề khi có nhiều người truy cập hoặc 
có quá nhiều trang Web động phải tốn thời gian để tính toán cho ra kết quả. 
Web Servercó xu hướng tận dụng ưu điểm của 2 phương pháp khác nhau để giải quyết vấn đề này là: đa tiểu trình (multi-threading)
hoặc đa tiến trình (multiprocessing) hoặc các hệ lai giữa chúng.

# 2.Các modules trong Apache

  Apache được thiết kế theo lối modules nó bao gồm 1 modules core đóng vai trò trung tâm và các modules khác là vệ tinh hỗ trợ trong quá trình sử lý . Các modules không liên hệ trực tiếp với nhau mà thông qua core 
  
Các module của Apache

Mặc định, sau khi cài đặt, trong Apache có đi kèm sẵn một số module để thực thi nhiệm vụ của một web server. Các module này, xếp theo thứ tự từng giai đoạn xử lý bao gồm:

**Chuyển đổi giữa URI thành filename trên server**

- Mod_userdir: chuyển thư mục home cho từng user.
- Mod_rewrite: điều chỉnh lại đường dẫn URL.
- Giai đoạn Xác thực / phân quyền

- mod_auth, mod_auth_anon,mod_auth_db, mod_auth_dbm: các kiểu xác thực người dùng.
- Mod_access: kiểm soát truy nhập theo từng host.

**Xác định MIME của đối tượng được truy vấn**

- mod_mime: xác định loại file bằng cách dựa vào phần mở rộng.
- mod_mime_magic: xác định loại file bằng cách sử dụng “magic number”

**Chỉnh sửa đường dẫn**

- Mod_alias: thay thế alias bằng đường dẫn thực trên server.
- Mod_env: thay đổi các tham số hệ thống dựa trên thông tin trong file cấu hình.
- Mod_spelling: tự động sửa lỗi trong URL.

**Gửi trả lại dữ liệu cho client**

- Mod_actions: các script cho từng loại file sẽ được thực thi.
- Mod_asis: gửi file nguyên dạng
- Mod_autoindex:
- Mod_cgi: gọi script CGI và trả lại kết quả.
- Mod_include:
- Mod_dir: xử lý về thư mục
- Mod_imap: xử lý image-map files.

**Ghi log**

- Mod_log_*: các module log khác nhau.

**Các module quan trọng đối với Apache Server**

- httpd_core: Chứa các chức năng cốt lõi của Apache, cần thiết cho bất cứ Apache nào.
- mod_access: Cung cấp chế độ khiển tác dựa trên tên máy, địa chỉ IP, hoặc các tính chất yêu cầu thuộc về các clients. Bởi vì - module này cần cho các chỉ phối (directive) “order”, “allow” và “deny”, nó cần được cho phép.
- mod_auth: Cần thiết để ứng dụng vấn đề khai báo người dùng cho việc sử dụng các hồ sơ nguyên bản (khai báo căn bản cho HTTP), được chỉ định trong chức năng trù bị.
- mod_dir: Cần thiết để tìm kiếm và phục vụ các hồ sơ thư mục: “index.html”, “default.htm”, v..v..
- mod_log_config: Cần thiết để ứng hiệu báo cáo những yêu cầu thực hiện đến server.
- mod_mime: Cần thiết để chỉnh lý nhóm chữ cái, mã hoá nội dung, tùy tác ngôn ngữ nội dung và các loại MIME đại diện cho các loại tài liệu.
- Module httpd_core

Module này đóng vai trò đảm nhiệm các chức năng chính của Web Server. Các Directive bao gồm:

- DefaultType
- DocumentRoot
- MaxClients
- Modules
- Port
- ServerAdmin
- ServerName
- ServerRoot
- SocketType
- SSLCertificateFile
- SSLCertificateKeyFile
- SSLVerifyClient

# 3.Cấu hình webserver Apache
**Website mặc định**

  Mặc định website của bạn cần lưu trong địa chỉ /var/www/html và file mặc định là index.html. Để thử nghiệm, bạn upload một website.
  
![Imgur](http://i.imgur.com/71agG0f.png)
 
  Bạn có nhiều giải pháp cho việc upload một website lên webserver, FTP là một gợi ý tốt. Nếu muốn đơn giản hơn thì bạn dùng một tiện ích SSH nào đó để gửi file lên. Ở đây, tôi giả định rằng bạn có thể thực hiện được những đều đó.
  
  Sau đó bạn chỉ cần thử lại webserver của mình bằng cách truy cập địa chỉ ip của server, ví dụ ở đây là 92.168.40.131.
  
  ![Imgur](http://i.imgur.com/zIoGD4N.png)
  
  
