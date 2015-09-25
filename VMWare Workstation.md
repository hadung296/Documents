#  VMWare Workstation 
  VMWare Workstation  là 1 chương trình máy ảo được sử dụng phổ biến và rộng rãi. Hỗ trợ người dùng nhiều tùy chọn .
Đây thực sự là công cụ hữu ích cho các lập trình viên, chuyên gia quản trị hệ thống và cả những người dùng cá nhân khi muốn 
khám phá, thử nghiệm.Máy tính ảo, đúng với tên gọi nó có mọi chức năng như một máy tính bình thường chỉ khác một điều là máy
tính ảo chạy trên nền của máy tính thật. Một máy tính thật chạy phần mềm VMware Workstation có thể hỗ trợ vô số các máy ảo
chạy trên nó với giới hạn chỉ là ở dung lượng ổ cứng. Các máy tính ảo có thể chạy đồng thời số lượng tùy thuộc vào lượng bộ nhớ 
RAM của hệ thống thật, thậm chí các máy ảo này còn có thể liên lạc với nhau tạo thành một mô hình mạng ảo. Với phần mềm ảo hóa,
thì nhà quản trị hệ thống có thể cài đặt một máy ảo chạy hệ điều hành mới để kiểm tra tính ổn định, các chuyên gia phát triển
phần mềm có thể kiểm tra sản phẩm của mình chạy trên nền những hệ điều hành khác nhau một cách nhanh nhất, những nhà nghiên 
cứu phần mềm độc hại có thể phân tích một virus mới mà không hề gây tổn hại đến máy tính thật và người dùng bình thường có thể 
chạy các phần mềm mà chỉ có thể chạy trên các hệ điều hành cũ.
  
  **Cách sử dụng VMWare Workstation :**
  
  ![](http://i.imgur.com/Y8xL3TF.png "giao dien chính")
- Các tùy chọn :
<ul>
<li>Create a new virtual Machine : Tạo máy ảo mới từ file cài đặt 
<li>Open a virtual Machine : Mở 1 máy ảo từ thư mục cài đặt trước 
<li>connect to remote server : kết nối từ máy chủ 
<li>Connect to VMWare vCloud air : kết nốitừ đám mây .
</ul>

**Cài đặt 1 máy ảo từ file cài đặt**
 ![Imgur](http://i.imgur.com/cx2tnvU.png)
 Chọn file > New virtual Machine 
 
 ![Imgur](http://i.imgur.com/ya1xnLV.png)
Custum > next
 
 ![Imgur](http://i.imgur.com/lwnkupQ.png)
Next
 
 ![Imgur](http://i.imgur.com/TLfJ3c1.png)
Chọn đường dẫn tới File cài đặt (iso) >Next 

![Imgur](http://i.imgur.com/QiDKgL7.png "Đặt tên cho máy ảo ")
Đặt tên cho máy ảo 

![Imgur](http://i.imgur.com/ZJNPhiy.png)
Thiết lập số nhân dùng 

![Imgur](http://i.imgur.com/jSEgWup.png)
Thiết lập Ram sử dụng 

![Imgur](http://i.imgur.com/hARctus.png)
Chọn chế độ mạng 

![Imgur](http://i.imgur.com/EKlWWMp.png) Next
![Imgur](http://i.imgur.com/vk3uVSc.png) Next

![Imgur](http://i.imgur.com/3vXOQ0b.png)
Tạo 1 ổ đĩa quản lý.

![Imgur](http://i.imgur.com/hR94XNn.png)
Thiết lập dung lượng ổ đĩa 

![Imgur](http://i.imgur.com/ZpYVqdf.png)
![Imgur](http://i.imgur.com/OtAcTKs.png)
Có thể chọn Customize hardware để thiét lập thêm 1 số tùy chọn > finish. 

## ** Các chế độc card mạng trong VMWare Workstation**

![Imgur](http://i.imgur.com/G7g9jfA.png)

- các tùy chọn :
<ul>
<li> bridge :card này sử dụng chính card mạng thật của chúng ta để kết nối ra ngoài Internet (card ethernet hoặc wireless). Do đó khi sử dụng card mạng này IP của máy ảo sẽ cùng với dải IP của máy thật.
<li> NAT : card này Nat địa chỉ IP của máy thật để máy ảo sử dụng kết nối ra ngoài internet .
<li> Host only : Cho người sử dụng có thể tự cấu hình IP cho máy ảo .
</ul>
 
- Chúng ta có thể add thêm các card mạng hoặc lược bỏ đi 1 số card mạng ở mục add network và remove network .
- Để cấu hình Ip cho máy ảo chọn Host only ở đây ta có thể cấu hình DHCP và đặt IP cũng như SUBNET MARK .

![Imgur](http://i.imgur.com/05TLhgH.png)
![Imgur](http://i.imgur.com/RAuzgnI.png)





 
 
 
  
  
