# CNTT1-nh-p-m-n-c-ng-ngh-th-ng-tin-Session05_EXontap
Dưới đây là đáp án cô đọng, viết đúng kiểu bài làm của sinh viên:

---

## Phần 1 – CLI vs GUI và cấu trúc câu lệnh

1. **Phân tích lệnh `ls -Force C:\Windows\Logs`:**
* **Command:** `ls`
* **Options/Flags:** `-Force`
* **Argument:** `C:\Windows\Logs`


2. **Lý do dùng Terminal trên Cloud:**
* Máy chủ Server thường loại bỏ GUI để tiết kiệm RAM/CPU, bắt buộc quản trị qua CLI để tối ưu hiệu năng.



---

## Phần 2 – Điều hướng hệ thống file

1. **Chuyển vào thư mục bằng Relative Path:**
* `cd quan-ly-sinh-vien`


2. **Absolute Path tới `main.py`:**
* `C:\Users\student\Desktop\quan-ly-sinh-vien\src\main.py`


3. **Xem file ẩn ở `data\` khi đang đứng ở `src\`:**
* `ls -Force ..\data`



---

## Phần 3 – Thao tác file và thư mục

1. **Tạo cùng lúc 2 thư mục con (kèm folder cha):**
* `mkdir quan-ly-sinh-vien\src, quan-ly-sinh-vien\data`


2. **Tạo 3 file rỗng cùng lúc:**
* `New-Item quan-ly-sinh-vien\src\main.py, quan-ly-sinh-vien\src\utils.py, quan-ly-sinh-vien\README.md`


3. **Đổi tên và Backup thư mục:**
* Đổi tên: `mv quan-ly-sv quan-ly-sinh-vien`
* Backup đệ quy: `cp -Recurse quan-ly-sinh-vien backup-quan-ly-sinh-vien`



---

## Phần 4 – Xử lý lỗi Terminal

1. **Log lỗi 2 (`cd scr`):**
* **Chẩn đoán:** Lỗi gõ sai chính tả (Typo) tên thư mục.
* **Mẹo dùng phím Tab:** Gõ `cd s` rồi bấm **Tab**, nếu PowerShell không gợi ý ra `src` tức là gõ sai hoặc chưa tạo thư mục.


2. **Log lỗi 3 (`Access is denied`):**
* **Chẩn đoán:** Lỗi bị chặn bởi chính sách Security / Execution Policy của Windows.
* **Khắc phục:** Chạy lệnh `Set-ExecutionPolicy Unrestricted -Scope Process` rồi nhấn `Y`.


3. **Log lỗi 1 (Cảnh báo xóa folder `old-version`):**
* **Chẩn đoán:** Thư mục có chứa file con bên trong nên PowerShell hỏi để tránh xóa nhầm.
* **Đơn thuốc:** `rm -Recurse -Force old-version`


4. **Đọc log lỗi 4 theo 3 bước:**
* **(a) Dòng báo lỗi trực tiếp:** `FileNotFoundError: [Errno 2] No such file or directory: 'data/input.csv'`
* **(b) Từ khóa lỗi:** `FileNotFoundError`
* **(c) Điều cần kiểm tra:** Vị trí hiện tại đang đứng ở `src\`. Code gọi đường dẫn tương đối `data/input.csv` sẽ bị sai do không tìm thấy thư mục `data` bên trong `src` (sửa code thành `../data/input.csv` hoặc lùi ra thư mục gốc trước khi chạy).
