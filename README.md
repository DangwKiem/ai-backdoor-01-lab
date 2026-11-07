# AI Backdoor 01

Bài thực hành Labtainers về kiểm tra SHA-256, phân tích hành vi của hai mô hình ONNX, xác minh trên SecureMail AI và khôi phục mô hình trong staging. Thời lượng dự kiến 90–120 phút.

## Cài bằng IModule

Trong terminal host của Labtainers trên Linux x86-64 hoặc VM Labtainers x86-64, chạy:

```bash
cd "$LABTAINER_DIR/scripts/labtainer-student"
imodule https://raw.githubusercontent.com/DangwKiem/ai-backdoor-01-lab/main/imodule.tar
labtainer ai-backdoor-01
```

Lần đầu chạy, Labtainers tải hai image từ Docker Hub. Nếu có thông báo xác nhận tải image, nhập `y`. SecureMail AI tự khởi động cùng lab để bạn làm đủ bốn nhiệm vụ.

Nếu đã chạy bản cũ, lưu bài và chạy `stoplab` trước khi cập nhật. Dùng `imodule -u`, tải image analyst mới bằng `docker pull dangkiem/ai-backdoor-01.ai-backdoor-01.student:latest` rồi chạy `labtainer -r ai-backdoor-01`. Tùy chọn `-r` tạo lại container và xóa phiên làm cũ.

## Cài từ ZIP và tự dựng image

Chuẩn bị một bản Labtainers có giao diện đồ họa, Docker và bộ công cụ Designer. Nếu thiếu lệnh `rebuild`, chạy `./update-designer.sh` từ `$LABTAINER_DIR/setup_scripts` rồi mở lại terminal.

Tải [ai-backdoor-01-labtainers.zip](ai-backdoor-01-labtainers.zip) từ GitHub. Trong terminal host, thay đường dẫn ví dụ bằng đường dẫn đến tệp đã tải. Lần dựng đầu tiên cần Internet để tải image nền và thư viện Python.

```bash
unzip -n /path/to/ai-backdoor-01-labtainers.zip -d "$LABTAINER_DIR/labs"
cd "$LABTAINER_DIR/scripts/labtainer-student"
rebuild ai-backdoor-01
```

Lệnh `rebuild` khởi động lab sau khi dựng image.

## Làm bài

Trong một terminal của container `analyst`, mở hướng dẫn chi tiết:

```bash
cd ~/ai-backdoor
less README.md
```

Ở các phiên tiếp theo, mở lab bằng `labtainer ai-backdoor-01` từ terminal host. Với nhiệm vụ 3, mở Firefox trong container `analyst`:

```bash
firefox --private-window http://172.29.61.20:8080/ &
```

Đăng nhập bằng **`student`** và **`lab-practice`**. Web sinh khóa HMAC riêng cho mỗi phiên bản lab. Mã nhận được dùng làm minh chứng thực hành.

## Kiểm tra và nộp bài

Từ terminal host, chạy `checkwork` để kiểm tra các mục minh chứng. Khi hoàn thành, chạy `stoplab` và nộp tệp `.lab` theo đường dẫn được in ra.
