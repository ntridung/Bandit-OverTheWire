
``` bash
ssh -p 2220 banditX@bandit.labs.overthewire.org
```
template
``` md
# Level  -> Level 
### Mục tiêu

### Kiến thức áp dụng

## Cách giải

## Đáp án

## Password

```


# Level 0 -> Level 1

## Mục tiêu 
Tìm mật khẩu trong file readme trong thư mục home.
## Kiến thức áp dụng 
*  [[ls]]
*  [[cat]]
## Cách giải 
Đầu tiên, kiểm tra các file trong thư mục hiện tại 
## Đáp án
``` bash 
ls 
cat readme
```
## Password
``` 
6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
```

# Level 1 -> Level 2

## Mục tiêu 
Mở được file '-' trong home

## Kiến thức áp dụng
* [[cat]]

## Cách giải
Dùng cat ./ để mở file

## Đáp án 
``` bash 
ls 
cat ./-
```
## Password
``` 
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
```

# Level 2  -> Level 3

## Mục tiêu 
Mở được file có dấu cách trong home

## Kiến thức áp dụng
* [[cat]]

## Cách giải
To use the `cat`  command one, you must wrap the filename in quotation marks (" ") or escape the spaces (this \ is \ space.txt).\

## Đáp án
``` bash
bandit2@bandit:~$ cat ./"--spaces in this filename--" 
```
## Password
```
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
```

# Level 3 -> Level 4
### Mục tiêu
Mở được file hidden trong thư mục inhere

### Kiến thức áp dụng
* [[ls]]
## Cách giải
Dùng ls -a để tìm các file ẩn
## Đáp án
```bash 
cd inhere
ls -a
	cat ...Hiding-From-You
```

## Password
```
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
```

# Level 4 -> Level 5
### Mục tiêu
Tìm được file có nội dung mà con người đọc được ( human-readable) trong inhere

### Kiến thức áp dụng
* [[file]]
* [[ls]]
## Cách giải
Dùng file để tìm xem định dạng bên trong tất cả các file và dùng cat ./ để mở 
## Đáp án
``` shell
cd inhere
ls -a 
file ./-file*
cat ./-file07
```

## Password
```
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
```

# Level 5 -> Level  6
### Mục tiêu
Tìm file có : 
* Định dạng người đọc được ( Human-readable)
* Kích thước 1033 byte
* Không thể giải nén (not executable)

### Kiến thức áp dụng
* [[find]]
## Cách giải
Dùng option  : 
* -type f 
* -size
* ! -excutable
## Đáp án
``` shell
cd inhere
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```
## Password
```
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

```