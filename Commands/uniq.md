# Filter adjacent matching lines from INPUT (or standard input), writing to OUTPUT (or standard output).
# Cú pháp
``` shell
uniq [OPTION] [INPUT] [OUTPUT]
```

# OPTION
- -c (count) : thêm số lần xuất hiện vào đầu dòng
- -u (unique) : chỉ in những dòng xuất hiện 1 lần
- -d (duplicate) : chỉ in những dòng xuất hiện nhiều lần
# Cách hoạt động 
- nó sẽ lọc lấy các từ gần nhau và giống nhau trong file để chọn ra unique nếu không liền kề nhau thì nó không nhận ra (bởi thế ngta hay kết hợp [sort](Commands/sort) để cho ra kết quả đúng hơn).
VD : 
``` shell
nano text 

1
2
3
1
2
3
1
1
```
sau khi dùng uniq xuất ra :
``` shell
uniq text
1
2
3
1
2
3
1
```
nếu thêm sort :
``` shell
sort text | uniq

1
2
3
```