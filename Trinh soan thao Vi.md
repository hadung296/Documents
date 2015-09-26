#**Trình soạn thảo Vi**
Vi là trình soạn thảo hay được những người sử dụng những HĐH họ Linux dùng .

*Làm việc với Vi*

- Đê làm việc với 1 filư có sẵn hay1 file mới với Vi ta sử dụng câu lệch : Vi "tên tệp tin".
- Trong vi có 2 chế độ chỉnh sửa là i(insert) và a (command) để thoát khỏi chế độ này ta dùng phím ESC .
- Sử dụng lệnh h j k l hoặc các phím mũi tên tương ứng để di chuyển con trỏ sang trái, xuống, lên, sang phải.
- Sử dụng lệnh x để xóa 1 kí tự , dw để xóa 1từ , dd để xóa 1 dòng .( sử dụng số trước các lệnh để thực thi số lần của câu lệnh đó
ví dụ : 3x là xóa 3 kí tự , 2dw để xóa 2  từ sau con trỏ).
- Sử dụng câu lệch u để phục hồi lại (Undo)
- Để sao chép ta sử dụng lệnh yy (hoặc _yy trong đó _ là số các dong sao chép ví dụ 3yy để sao chép 3 dòng ) và sau đó dùng lệch p 
để dán.
- Để nhảy tới dòng ta sử dụng _G ( _ là số dòng muốn tới ví dụ muốn tới dòng 12 ta bấm 23G) . Để nhảy tới cột _| ( ví dụ nhảy tới
cột 4 ta bấm 4| ) . để nhảy tới dòng cuối dùng lệnh G.
- :set nu hiển thị số dòng trước mỗi dòng, et nonu để bỏ hiển thị số dòng.
– :1,8d xóa từ dòng 1 cho đến dòng 8 trong file.
– :8,16 co 32 để copy dòng 8 đến 16 đến điểm sau dòng 32.
– :3,16 m 32 để chuyển rời dòng 8 đến 16 đến điểm sau dòng 32.
- Để lưu và thoát sử dụng :wq để thoát kg lưu ta dùng :q!
* Sau đây là 1 vài hình ảnh về vi trên ubuntu server *
![](http://i.imgur.com/Zrd6szH.png)
![Imgur](http://i.imgur.com/ljh56Le.png)
![Imgur](http://i.imgur.com/isHWaVh.png)

