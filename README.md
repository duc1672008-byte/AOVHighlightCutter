# AOV Highlight Cutter

Ứng dụng Android mẫu để quét video trận Liên Quân, nhận diện thông báo hạ gục bằng OCR và xuất các đoạn video ngắn quanh thời điểm phát hiện.

## Tính năng
- Chọn video từ điện thoại.
- Quét các khung hình theo khoảng thời gian do người dùng chọn.
- Dùng Google ML Kit Text Recognition để tìm các cụm từ như `DOUBLE KILL`, `TRIPLE KILL`, `QUAD KILL`, `PENTA KILL`, `SHUT DOWN`, `LEGENDARY`, `HẠ GỤC`, `SIÊU VIỆT`.
- Xuất clip quanh mỗi mốc phát hiện bằng Android MediaExtractor/MediaMuxer (không cần FFmpeg).
- Giữ nguyên độ phân giải/tỷ lệ khung hình gốc.

## Giới hạn
- Đây là bản MVP; OCR phụ thuộc vào ngôn ngữ/hiển thị trong video và có thể bỏ sót hoặc nhận nhầm.
- Quét mẫu mỗi 1.5 giây mặc định; có thể tăng/giảm trong giao diện.
- Cắt clip bằng stream-copy, nên điểm bắt đầu thực tế có thể lùi tới keyframe gần nhất.
- Video có codec/định dạng không tương thích với MediaMuxer có thể không xuất được.
- Chưa được kiểm thử trên mọi thiết bị Android. Không coi là bản đã xác minh trước khi chạy build và thử trên thiết bị thực.

## Build APK
1. Mở repository trên GitHub.
2. Đưa toàn bộ nội dung thư mục này vào thư mục gốc của repository (không tải ZIP như một file duy nhất).
3. Mở tab **Actions** và chạy workflow **Build Android APK**; workflow cũng tự chạy khi push lên `main`.
4. Mở lần chạy thành công, vào **Artifacts**, tải `AOVHighlightCutter-debug-apk`, giải nén và cài APK.

Yêu cầu Android Studio/Gradle: Android Gradle Plugin 8.7.3, JDK 17.
