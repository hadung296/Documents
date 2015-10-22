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
- 

