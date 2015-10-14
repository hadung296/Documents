# Nguyên tắc sử lý của webserver 

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

# Cấu hình webserver apache 

