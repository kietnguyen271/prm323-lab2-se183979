# Design Decisions - TeamUp EXE

Mỗi quyết định gắn với persona (Khang/Linh), heuristic Nielsen hoặc ràng buộc kỹ thuật. Cần 3-5 ví dụ, có đủ Accept, Modify và Reject.

## Quyết định 1: ____ (Accept / Modify / Reject)
- Đề xuất của AI (Prompt/vòng nào, màn nào): ____
- Quyết định và lý do (persona / heuristic / ràng buộc): ____
- Thay đổi trong Figma (page, frame): ____

## Quyết định 2: ____ (Accept / Modify / Reject)
(cấu trúc như trên)

## Quyết định 3: ____ (Accept / Modify / Reject)
(cấu trúc như trên)

## Gợi ý để tìm quyết định Reject / Modify thật
- AI thêm tính năng chat trong app: ngoài phạm vi, nên Reject.
- AI để cả dãy chip lọc chiếm màn hình: Modify thành bottom sheet.
- AI dùng chữ cam trên nền trắng: Reject vì contrast thấp.
(Chỉ ghi nếu Stitch thật sự sinh ra điều này.)

## Bằng chứng accessibility
| Hạng mục | Cách kiểm | Kết quả | Ảnh chứng |
|---|---|---|---|
| Contrast chữ thường ≥4.5:1 | WebAIM Contrast Checker | | |
| Contrast chữ lớn/điều khiển ≥3:1 | WebAIM | | |
| Tap target ≥48×48 dp | Đo trong Figma | | |
| Chữ nội dung ≥14 sp | Kiểm Typography | | |
| Không chỉ dùng màu | Trạng thái có icon + chữ | | |
| Khung 360 dp | Frame 360×800 | | |
| Khung 412 dp | Frame 412×915, không vỡ layout | | |