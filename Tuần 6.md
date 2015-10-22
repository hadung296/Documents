#Nghiên cứu dịch vụ DNS 
**1.DNS**

  DNS là từ viết tắt trong tiếng Anh của Domain Name System, là Hệ thống phân giải tên miền được phát minh vào năm 1984 cho 
Internet, chỉ một hệ thống cho phép thiết lập tương ứng giữa địa chỉ IP và tên miền.

**2.Chức năng của DNS**

  Mỗi Website có một tên ( là tên miền hay đường dẫn URL : Universal Resource Locator ) và một địa chỉ IP. Địa chỉ IP gồm 4 
nhóm số cách nhau bằng dấu chấm. Khi mở một trình duyệt Web và nhập tên website, trình duyệt sẽ đến thẳng website mà không
cần phải thông qua việc nhập địa chỉ IP của trang web. Quá trình "dịch" tên miền thành địa chỉ IP để cho trình duyệt hiểu và
truy cập được vào website là công việc của một DNS server. Các DNS trợ giúp qua lại với nhau để dịch địa chỉ "IP" thành "tên"
và ngược lại. Người sử dụng chỉ cần nhớ "tên", không cần phải nhớ địa chỉ IP ( địa chỉ IP là những con số rất khó nhớ ).

**3.Nguyên tắc làm việc**

- Mỗi nhà cung cấp dịch vụ vận hành và duy trì DNS server riêng của mình, gồm các máy bên trong phần riêng của mỗi nhà cung cấp
dịch vụ đó trong Internet. Tức là, nếu một trình duyệt tìm kiếm địa chỉ của một website thì DNS server phân giải tên website này
phải là DNS server của chính tổ chức quản lý website đó chứ không phải là của một tổ chức ( nhà cung cấp dịch vụ ) nào khác.
- INTERNIC ( Internet Network Information Center ) chịu trách nhiệm theo dõi các tên miền và các DNS server tương ứng. INTERNIC là một tổ chức được thành lập bởi NFS ( National Science Foundation ), AT&T và Network Solution, chịu trách nhiệm đăng ký các tên miền của Internet. INTERNIC chỉ có nhiệm vụ quản lý tất cả các DNS server trên Internet chứ không có nhiệm vụ phân giải tên cho từng địa chỉ.
- DNS có khả năng tra vấn các DNS server khác để có được một cái tên đã được phân giải. DNS server của mỗi tên miền thường có hai việc khác biệt. Thứ nhất, chịu trách nhiệm phân giải tên từ các máy bên trong miền về các địa chỉ Internet, cả bên trong lẫn bên ngoài miền nó quản lý. Thứ hai, chúng trả lời các DNS server bên ngoài đang cố gắng phân giải những cái tên bên trong miền nó quản lý.
- DNS server có khả năng ghi nhớ lại những tên vừa phân giải. Để dùng cho những yêu cầu phân giải lần sau. Số lượng những tên phân giải được lưu lại tùy thuộc vào quy mô của từng DNS.

**4.Cách sử dụng**

  Do các DNS có tốc độ biên dịch khác nhau, có thể nhanh hoặc có thể chậm, do đó người sử dụng có thể chọn DNS server để sử dụng cho riêng mình. Có các cách chọn lựa cho người sử dụng. Sử dụng DNS mặc định của nhà cung cấp dịch vụ ( internet ), trường hợp này người sử dụng không cần điền địa chỉ DNS vào network connections trong máy của mình. Sử dụng DNS server khác ( miễn phí hoặc trả phí ) thì phải điền địa chỉ DNS server vào network connections. Địa chỉ DNS server cũng là 4 nhóm số cách nhau bởi các dấu chấm.
  
**5.Cấu trúc gói DNS**

- ID QR Opcode AA TC RD RA Z Rcode
- QDcount ANcount NScount ARcount
- ID: Là một trường 16 bits, chứa mã nhận dạng, nó được tạo ra bởi một chương trình để thay cho truy vấn. Gói tin hồi đáp sẽ dựa vào mã nhận dạng này để hồi đáp lại. Chính vì vậy mà truy vấn và hồi đáp có thể phù hợp với nhau.
- QR: Là một trường 1 bit. Bít này sẽ được thiết lập là 0 nếu là gói tin truy vấn, được thiết lập là một nếu là gói tin hồi đáp.
- Opcode: Là một trường 4 bits, được thiết lập là 0 cho cờ hiệu truy vấn, được thiết lập là 1 cho truy vấn ngược, và được thiết lập là 2 cho tình trạng truy vấn.
- AA: Là trường 1 bit, nếu gói tin hồi đáp được thiết lập là 1, sau đó nó sẽ đi đến một server có thẫm quyền giải quyết truy vấn.
- TC: Là trường 1 bit, trường này sẽ cho biết là gói tin có bị cắt khúc ra do kích thước gói tin vượt quá băng thông cho phép hay không.
- RD: Là trường 1 bit, trường này sẽ cho biết là truy vấn muốn server tiếp tục truy vấn một cách đệ qui.
- RA: Trường 1 bit này sẽ cho biết truy vấn đệ qui có được thực thi trên server không .
- Z: Là trường 1 bit. Đây là một trường dự trữ, và được thiết lập là 0.
- Rcode: Là trường 4 bits, gói tin hồi đáp sẽ có thể nhận các giá trị sau :
<ul>
<li>0: Cho biết là không có lỗi trong quá trình truy vấn.
<li>1: Cho biết định dạng gói tin bị lỗi, server không hiểu được truy vấn.
<li>2: Server bị trục trặc, không thực hiện hồi đáp được.
<li>3: Tên bị lỗi. Chỉ có server có đủ thẩm quyền mới có thể thiết lập giá trị náy.
<li>4: Không thi hành. Server không thể thực hiện chức năng này .
<li>5: Server từ chồi thực thi truy vấn.
</ul>
- QDcount: Số lần truy vấn của gói tin trong một vấn đề.
- ANcount: Số lượng tài nguyên tham gia trong phần trả lời.
- NScount: Chỉ ra số lượng tài nguyên được ghi lại trong các phẩn có thẩm quyền của gói tin.
- ARcount: Chỉ ra số lượng tài nguyên ghi lại trong phần thêm vào của gói tin.

