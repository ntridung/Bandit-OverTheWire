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
