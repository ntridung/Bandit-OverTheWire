# DÒNG CHẢY DỮ LIỆU & CHUYỂN HƯỚNG (REDIRECTION) IN LINUX

---

## 1. Ba Luồng Tiêu Chuẩn (Standard Streams)

| Tên luồng | Mã FD | Tên đầy đủ | Mặc định | Chức năng |
| :--- | :---: | :--- | :--- | :--- |
| **`stdin`** | `0` | Standard Input | Bàn phím | Đầu vào dữ liệu của lệnh |
| **`stdout`** | `1` | Standard Output | Màn hình | Đầu ra chứa kết quả đúng |
| **`stderr`** | `2` | Standard Error | Màn hình | Đầu ra chứa thông báo lỗi / cảnh báo |

---

## 2. Các Toán Tử Chuyển Hướng Phổ Biến

### A. Đầu vào (`stdin`)
* `command < file`: Truyền nội dung từ `file` vào `stdin` của lệnh.
* `command <<< "text"`: Truyền trực tiếp một chuỗi văn bản/biến vào `stdin` (*Here String*).
* `command << EOF ... EOF`: Truyền nhiều dòng văn bản vào `stdin` (*Here Document*).

### B. Đầu ra (`stdout` & `stderr`)
* `command > file`: Ghi `stdout` vào file (ghi đè).
* `command >> file`: Nối `stdout` vào cuối file (ghi tiếp).
* `command 2> file`: Ghi lỗi (`stderr`) vào file.
* `command 2>/dev/null`: Bỏ hoàn toàn thông báo lỗi (ném vào "hố đen").
* `command > file 2>&1` *(hoặc `command &> file`)*: Gộp cả `stdout` và `stderr` lưu vào cùng 1 file.

### C. Kết nối lệnh
* `commandA | commandB` *(Pipe)*: Chuyển `stdout` của lệnh A làm `stdin` cho lệnh B.
* `command | tee file`: Vừa in `stdout` ra màn hình, vừa lưu vào file.

---

## 3. File Ảo Hệ Thống Hay Dùng

* `/dev/null`: "Hố đen" dữ liệu, dùng để hủy dữ liệu không muốn thấy.
* `/dev/stdin`: Đại diện cho luồng đầu vào.
* `/dev/stdout`: Đại diện cho luồng đầu ra chuẩn.
* `/dev/stderr`: Đại diện cho luồng báo lỗi.

---

## 4. Mẹo Lệnh Nhanh (Examples)

```bash
# Tìm kiếm bỏ qua lỗi Permission denied
find / -name "filename" 2>/dev/null

# So sánh output 2 lệnh trực tiếp không cần tạo file tạm
diff <(command1) <(command2)

# Vừa xem kết quả vừa nối tiếp vào cuối file
ls -la | tee -a log.txt
```

## 5. Piping (Đường ống)
 >Feed the output from the program on the left as input to the program on the right
Chỉ đơn gian là bỏ qua bước lưu trữ trong quá trình : tạo ra -> lưu trữ -> xử lý -> in ra