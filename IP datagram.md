# IP datagram 

Dữ liệu truyền qua internet qua giao thức Ip qua các gói tin gọi là ip datagram .Giống như các giao thức mạng khác ip sử dụng 1
định dạng cụ thể cho gói tin của nó cụ thể ở đây là IP version 4 (IPv4) .

- Các datagram IPv4 được chia thành 2 phần :
<ul>
<li> Header : Chứa các địa chỉ và kiểm soát gói tin
<li> Payload : Lấy dữ liệu thực tế gửi lên internet /
</ul>

Định dạng gói tin IP được mô tả :

![Imgur](http://i.imgur.com/EQF7SUJ.jpg)

- Version: Xác định các phiên bản của IP được sử dụng để tạo ra các gói tin. Đối với IPv4, đây là phiên bản 4. Mục đích của
việc này là để đảm bảo khả năng tương thích giữa các thiết bị có thể được chạy phiên bản khác nhau của IP. Nói chung, một 
thiết bị chạy một phiên bản cũ hơn của IP sẽ từ chối gói tin được tạo ra bởi việc triển khai mới, theo giả định rằng phiên bản 
cũ có thể không có khả năng để giải thích các datagram mới hơn một cách chính xác.
- Internet header Length (IHL): Chỉ định chiều dài của tiêu đề IP, nói cách 32-bit. Điều này bao gồm độ dài của bất kỳ trường
lựa chọn và padding. Giá trị bình thường của việc này khi không có tùy chọn được sử dụng là 5 (5 từ 32-bit = 5 * 4 = 20 byte)
Ngược lại với các con Total Length trường bên dưới.
- Loại Of Service (TOS): Mộ trươg được thiết kế để mang thông tin để cung cấp cho các tính năng dịch vụ, chẳng hạn như phân
phối ưu tiên, cho IP datagram. Nó không bao giờ được sử dụng rộng rãi như được xác định ban đầu, và ý nghĩa của nó đã được xác 
định lại sau đó để sử dụng bởi một kỹ thuật gọi là Differentiated Services (DS).
- Total length (TL): Chỉ định tổng chiều dài của gói tin IP, trong byte. Kể trường này này là 16 bit rộng, chiều dài tối đa 
của một gói tin IP là 65.535 bytes, mặc dù hầu hết đều ​​nhỏ hơn nhiều.
- Indentification :Trường này chứa một giá trị 16-bit cho mỗi đoạn thuộc về một thông điệp cụ thể; cho datagram ban đầu được
gửi unfragmented nó vẫn được điền vào, vì vậy nó có thể được sử dụng nếu các gói tin phải được phân mảnh bởi một bộ định 
tuyến trong thời gian giao hàng. Trường này được sử dụng bởi người nhận để lắp ráp lại tin nhắn mà không vô tình pha trộn 
các mảnh vỡ từ các thông điệp khác nhau. Điều này là cần thiết vì các mảnh vỡ có thể đến từ nhiều tin nhắn pha trộn với nhau,
kể từ khi gói dữ liệu IP có thể được nhận ra trật tự từ bất kỳ thiết bị.
- Flags :Một trường 3-bit sau và được sử dụng để kiểm soát hay xác định các mảnh vỡ. Chúng là (theo thứ tự, từ thứ tự cao thấp):
<ul>
<li>bit 0: Dành; phải bằng không.
<li>bit 1: Đừng DF (DF)
<li>bit 2: More Fragments (MF)
</ul>
Nếu cờ DF được thiết lập, và sự phân mảnh được yêu cầu để định tuyến các gói dữ liệu, sau đó các gói tin bị loại bỏ. 
Điều này có thể được sử dụng khi gửi các gói tin đến một máy chủ mà không có đủ nguồn lực để xử lý phân mảnh. Nó cũng có 
thể được sử dụng cho Path MTU Discovery, hoặc là tự động bởi các phần mềm máy chủ IP, hoặc bằng tay bằng cách sử dụng các 
công cụ chẩn đoán như ping hay traceroute. Đối với các gói unfragmented, cờ MF sẽ bị xóa. Đối với các gói tin bị phân mảnh,
tất cả các mảnh vỡ ngoại trừ cuối cùng có cờ đặt MF. Đoạn cuối cùng có một trường Fragment khác không Offset, phân biệt nó từ
một gói unfragmented.

- Fragment offset : Đoạn bù đắp có chiều dài 13 bit và xác định bù đắp của một đoạn cụ thể so với sự khởi đầu của ban datagram 
IP unfragmented
- Time To Live (TTL) : phiên bản ngắn: Chỉ định bao lâu gói tin được phép "sống" trên mạng, về các bước nhảy router. Mỗi router decrements giá trị của trường TTL (làm giảm nó bằng một) trước khi truyền nó. Nếu trường TTL xuống hết, các gói tin được giả định đã đi quá lâu một tuyến đường và bị loại bỏ. Xem dưới đây để giải thích dài hơn TTL.
- Checksum: Checksum tính trên tiêu đề để cung cấp bảo vệ cơ bản chống tham nhũng trong truyền tải. Đây không phải là mã CRC phức tạp hơn thường được sử dụng bởi các công nghệ lớp liên kết dữ liệu như Ethernet; nó chỉ là một checksum 16-bit. Nó được tính bằng cách chia các byte đầu vào từ (một từ là hai byte) và sau đó thêm chúng với nhau. Dữ liệu này không checksummed, chỉ là tiêu đề. Tại mỗi hop thiết bị nhận được datagram không tính toán checksum cùng và trên không phù hợp, loại bỏ các gói tin như bị hư hỏng.
- Source Address: : Địa chỉ IP 32-bit của người khởi của các datagram. Lưu ý rằng mặc dù các thiết bị trung gian như các bộ định tuyến có thể xử lý các gói tin, họ thường không đưa địa chỉ của họ vào lĩnh vực này, nó luôn luôn là thiết bị ban đầu gửi các gói tin.
- Destination Address::Địa chỉ IP 32-bit của người nhận của datagram. Một lần nữa, mặc dù các thiết bị như bộ định tuyến có thể là mục tiêu trung gian của gói tin, lĩnh vực này luôn luôn là cho đến cuối cùng.
- Options :Một hoặc nhiều hơn của một số loại tùy chọn có thể được bao gồm sau khi các tiêu đề tiêu chuẩn trong datagram IP nhất định 
- Padding: Nếu một hoặc nhiều tùy chọn mới có, và số lượng các bit được sử dụng đối với họ không phải là một bội số của 32, đủ không bit được thêm vào "pad ra" tiêu đề cho một bội số của 32 bit (4 byte).
- Data : Dữ liệu được truyền đi trong các gói tin, hoặc thông báo lớp cao hơn một toàn bộ hoặc một mảnh của một.
