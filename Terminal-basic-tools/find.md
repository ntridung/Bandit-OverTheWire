# Search for files in a directory hierarchy

-type : 
- f (Regular file): Tập tin thông thường (văn bản, hình ảnh, mã nguồn...).
- d (Directory): Thư mục.
- l (Symbolic link): Liên kết biểu tượng (phím tắt trỏ đến file khác).
- b (Block device): Thiết bị khối (như ổ đĩa cứng /dev/sda).
- c (Character device): Thiết thiết bị ký tự (như bàn phím, chuột).
- p (Named pipe): Đường ống có tên.
- s (Socket): Cổng kết nối mạng cục bộ. 
-size n[unit] :
- `c` : for bytes
- `b` : for 512 - byte block ( default)
- `w` : for two-byte words
- `k` : for kibibytes (KiB, units of 1024 bytes)
- `M` : for mebibytes (MiB, units of 1024 * 1024 = 1048576 bytes)
- `G` : for gibibytes (GiB, units of 1024 * 1024 * 1024 = 1073741824 bytes)
-executable : file có thể thực thi (hay gọi là chương trình)
-user [uname] : tìm file của user tên là uname 
-group [ugroup] : tìm file của group tên là ugroup
-readable : cũng giống executable nhưng là đọc

-exec [command] {} [ender] : thực thi lệnh command với cái path mà find tìm được
**VD** : `find / -user bandit7 -group bandit6 -size 33c -exec cat {} + 2>/dev/null`
+ {} (place holder) : nếu find đc cái path thì -exec [cmd] {} nó sẽ đưa cái path đó vào chổ {} để chạy [cmd]
+ [ender] có 2 loại : `/` và `+`
	+ `/` : Gọi lệnh [cmd] nhiều lần, mỗi lần cho đúng 1 file. (Mở quyển 1 ra đọc → Đóng lại. Mở quyển 2 ra đọc → Đóng lại...)
	+ `+` : Gom tất cả các file tìm được lại và truyền vào lệnh [cmd] trong 1 lần duy nhất.(Gộp quyển 1, quyển 2, quyển 3 lại rồi đọc hết một lượt)


Bonus : [[Standar_Streams_and_REdirection]]