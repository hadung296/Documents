#**A.Mô hình tham chiếu OSI 7 lớp ( Open systems Interconnection)**
-Mô hình này là cơ sở cho việc kết nối các hệ thống mở phục vụ cho các ứng dụng và di chuyển thong tin trong mạng .

<img src="blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>">

**1.Ưu điểm của OSI **
- Giảm độ phức tạp 
- Chuẩn hóa các sản phẩm 
- Dễ tìm hiểu và nghiên cứu 
- Tương thích vơi thiết bị 
- Thúc đấy công nghệ mạng 

**2. Chức năng các lớp**

**2.1.Physical(Lớp vật lý )**
- Đả bảo kết nối vật lý 
- Truyền tin dạng bit qua kênh vật lý 

**2.2.Data link (Lớp lien kết dữ liệu)**
Lớp này đảm bảo việc biến đổi các tin dạng bit từ lớp vật lý sang khung  số liệu và đảm bảo thong tin truyền lên lớp 3 không bị lỗi . Đảm bảo quản lý các thong tin số liệu và các thong tin trạng thái . 

**2.3.Network ( Lớp mạng )**
	Đảm bảo việc chuyển chính xác số liệu giữa thiết bị cuối trong mạng . Để làm được việc đó phải có chiến lược đánh địa chỉ thống nhất trong toàn mạng . Lớp mạng bảo đảm việc tìm đường tối ưu cho các gói dữ liệu bằng các giao thức dựa trên thiết bị router. Ngoài ra lớp mạng còn điều khiển dữ liệu lưu lượng trong mạng để trách tắc ngẽn. 

**2.4. Transport ( Lớp vận chuyển )**
	Lớp này nhận thong tin từ lớp session chia thành các gói tin nhỏ và chuyền xuống lớp dưới hoặc nhận thong tin từ lớp dưới và chuyển lên lớp session .Nhiệm vụ quan trọng là đảm bảo chuyển số liệu chính xác giữa 2 thực thể thuộc lớp phiên (session)  và điều khiển lưu lượng trách tắc nghẽn ở lớp mạng .

**2.5 Session ( Lớp phiên )**
	Liên kết giữa 2 thực thể có nhu cầu trao đổi dữ  liệu . chức năng quan trong của lớp phiên là đảm bảo đồng bộ số liệu bằng cách thực hiện điểm kiểm tra . tại các điểm kiểm tra này toàn bộ dữ liệu và trạng thái được lưu lại bộ nhớ đệm . Khi có sự cố sẽ khởi tạo lại phiên làm việc từ điểm kiểm tra cuối cùng 

**2.6. Presentation( Lớp thể hiện )**
	Nhiệm vụ là thích ứng các cấu trúc dữ liệu khác nhau của người dùng với cấu trúc dữ liệu thông nhất sử dụng trong mạng , nén và mã hóa ở lớp Presentation để chuyển xuống lớp dưới . Ngoài ra còn chứ các yêu  của người dùng , thư viện tiện ích …

**2.7 Application (Lớp ứng dụng )**
	Là lớp người dùng tương tác với môi trường OSI , đông thời cung cấp các dịch vụ và thông tin phân tán .
