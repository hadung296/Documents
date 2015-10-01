# Cấu trúc gói tin TCP 

Gói tin TCP gồm 2 phần 
- header
- Dữ liệu 

![Imgur](http://i.imgur.com/95YAaEe.png)

**1.Header**

Phần header có 11 trường trong đó 10 trường bắt buộc :
- Source port : Số hiệu cổng tại máy gửi (16 bit)
- Destination port : Số hiệu cổng ở máy nhận (16 bit)
- Sequence number :Trường này có 2 nhiệm vụ. Nếu cờ SYN bật thì nó là số thứ tự gói ban đầu và byte đầu tiên được gửi có số thứ
tự này cộng thêm 1. Nếu không có cờ SYN thì đây là số thứ tự của byte đầu tiên.(32bit)
- Acknowledgement number :Nếu cờ ACK bật thì giá trị của trường chính là số thứ tự gói tin tiếp theo mà bên nhận cần.(32bit)
- Data offset:Trường có độ dài 4 bít quy định độ dài của phần header (tính theo đơn vị từ 32 bít). Phần header có độ dài tối 
thiểu là 5 từ (160 bit) và tối đa là 15 từ (480 bít).
- Reserved :Dành cho tương lai và có giá trị là 0.
- Flags (hay Control bits) :Bao gồm 6 cờ:
<ul>
<li>URG :Cờ cho trường Urgent pointer
<li>ACK :Cờ cho trường Acknowledgement
<li>PSH :Hàm Push
<li>RST :Thiết lập lại đường truyền
<li>SYN :Đồng bộ lại số thứ tự
<li>FIN:Không gửi thêm số liệu
</ul>
- Window :Số byte có thể nhận bắt đầu từ giá trị của trường báo nhận (ACK)
- Checksum :16 bít kiểm tra cho cả phần header và dữ liệu. Nói một cách khác, tất cả các từ 16 bít được cộng với nhau. 
Kết quả thu được sau khi đảo giá trị từng bít được điền vào trường kiểm tra. Về mặt thuật toán, quá trình này giống với IPv4.
Điểm khác nhau chỉ ở chỗ dữ liệu dùng để tính tổng kiểm tra. Dưới đây là một header của IP:Các địa chỉ nguồn và đích là các
địa chỉ IPv4. Giá trị của trường protocol là 6 (giá trị dành cho TCP, xem thêm: Danh sách số hiệu giao thức IPv4). Giá trị 
của trường TCP length field là độ dài của toàn bộ phần header và dữ liệu của gói TCP.
- Urgent pointer :Nếu cờ URG bật thì giá trị trường này chính là số từ 16 bít mà số thứ tự gói tin (sequence number) cần dịch trái.
- Options :Đây là trường tùy chọn. Nếu có thì độ dài là bội số của 32 bít.

**2.Dữ liệu **

Trường cuối cùng không thuộc về header. Giá trị của trường này là thông tin dành cho các tầng trên (trong mô hình 7 lớp OSI).
Thông tin về giao thức của tầng trên không được chỉ rõ trong phần header mà phụ thuộc vào cổng được chọn.
