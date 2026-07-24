#  Quét qua toàn bộ tệp (dù là text, binary, hay file thực thi) và trích xuất tất cả các chuỗi ký tự đọc được (ASCII/Unicode).
# Cú pháp
``` shell
strings [OPTION] file_name
```
##  Nguyên lý hoạt động (How it works)
Mặc định, strings duyệt qua từng byte trong file theo thứ tự:
- Tiêu chuẩn nhận diện: Một chuỗi được coi là "đọc được" nếu nó bao gồm ít nhất 4 ký tự in được (printable characters - bao gồm chữ cái, chữ số, dấu câu, khoảng trắng) đứng liền nhau và kết thúc bằng một ký tự không in được (hoặc byte \0 - null terminator).
- Bỏ qua phần còn lại: Tất cả các byte dữ liệu nhị phân (machine code, pointer, compressed data) không thỏa mãn điều kiện trên sẽ bị bỏ qua
