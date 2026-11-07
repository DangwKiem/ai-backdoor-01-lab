# AI Backdoor 01

Bài thực hành Labtainers về kiểm tra SHA-256, phân tích hành vi của hai mô hình ONNX, xác minh trên SecureMail AI và khôi phục mô hình trong staging. Thời lượng dự kiến 90–120 phút.

## Cài trên máy Linux hoặc VM Labtainers

Chuẩn bị một bản Labtainers có giao diện đồ họa, Docker và bộ công cụ Designer. Nếu thiếu lệnh `rebuild`, chạy `./update-designer.sh` từ `$LABTAINER_DIR/setup_scripts` rồi mở lại terminal.

Tải [ai-backdoor-01-labtainers.zip](ai-backdoor-01-labtainers.zip) từ GitHub. Trong terminal host, thay đường dẫn ví dụ bằng đường dẫn đến tệp đã tải. Lần dựng đầu tiên cần Internet để tải image nền và thư viện Python.

```bash
unzip -n /path/to/ai-backdoor-01-labtainers.zip -d "$LABTAINER_DIR/labs"
cd "$LABTAINER_DIR/scripts/labtainer-student"
rebuild ai-backdoor-01
```

Lệnh `rebuild` khởi động lab sau khi dựng image. Trong một terminal của container `analyst`, mở hướng dẫn chi tiết:

```bash
cd ~/ai-backdoor
less README.md
```

Ở các phiên tiếp theo, mở lab bằng `labtainer ai-backdoor-01` từ terminal host. Nhiệm vụ 3 sử dụng URL SecureMail AI và mã đăng nhập riêng do giảng viên cung cấp. Các nhiệm vụ còn lại chạy trong container sinh viên.

## Kiểm tra và nộp bài

Từ terminal host, chạy `checkwork` để kiểm tra các mục minh chứng. Khi hoàn thành, chạy `stoplab` và nộp tệp `.lab` theo đường dẫn được in ra.
