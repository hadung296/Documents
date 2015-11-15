# Dùng putty để shh vào ubuntu server 

  SSH :

*Trên ubuntu server*

- Cài gói openssh-server với câu lệnh apt-get install openssh-server 
- Khởi động nó với lệnh : sudo /etc/init.d/shh start 
- Cấu hình shh : sudo vi /etc/shh/shhd_config

Sửa lại nội dung :

![Imgur](http://i.imgur.com/rXSVoZv.png)

- Lưu và khởi động lại : sudo /etc/init.d/shh start 

*Trên máy sử dụng win*

Tải putty http://the.earth.li/~sgtatham/putty/0.66/x86/putty.exe

