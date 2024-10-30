# Data-hiding-through-Steghide-images
![hird date](https://github.com/user-attachments/assets/3aa94c4a-0354-4466-89f1-4e9e85d1c749)

## 1. Cài đặt Steghide trên Linux
```bash
sudo apt update
sudo apt install steghide
```

## 2. Các chức năng chính của Steghide
- **Nhúng dữ liệu (Embedding)**: Giấu thông tin vào file ảnh hoặc âm thanh.
- **Trích xuất dữ liệu (Extracting)**: Lấy lại dữ liệu ẩn từ file.
- **Hiển thị thông tin (Info)**: Xem thông tin của file nền hoặc file đã nhúng dữ liệu.
- **Thuật toán mã hóa**: `steghide` hỗ trợ mã hóa dữ liệu bằng các thuật toán bảo mật.

## 3. Cách nhúng dữ liệu
Để nhúng file password.txt vào file ảnh im.jpeg:
```bash
steghide embed -cf im.jpeg -ef password.txt
```
**Tùy chọn**: 
- `-cf`: là file nền (cover file)
- `-ef`: là file cần nhúng.

Nhập mật khẩu khi được yêu cầu để bảo vệ dữ liệu nhúng.

Nếu muốn bỏ qua mật khẩu khi được yêu cầu để bảo vệ dữ liệu nhúng.
```bash
steghide embed -cf im.jpeg -ef password.txt -p node
```
- `-p node`: để bỏ qua mật khẩu.

## 4. Cách giải mã và trích xuất dữ liệu
Để trích xuất dữ liệu từ file im.jpeg:
```bash
steghide extract -sf stg.jpg
```
**Tùy chọn**: 
- `-sf` là file đã nhúng dữ liệu (stego file).
- Nhập mật khẩu đã sử dụng để giải mã dữ liệu và trích xuất file ban đầu.
