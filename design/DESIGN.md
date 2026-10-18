# DESIGN.md - TeamUp EXE

## Định hướng
App Android (Material 3) giúp sinh viên FPTU tìm nhóm EXE. Phong cách: sạch, thân thiện, học thuật, theme sáng, bo góc 12dp. Ngôn ngữ giao diện: tiếng Việt.

## Nguyên tắc thiết kế (gắn persona Khang)
1. Dùng một tay: bottom navigation 5 mục, nút hành động chính cố định ở đáy màn hình.
2. Giảm lo lắng deadline: đếm ngược deadline và trạng thái "của tôi" ở Home.
3. Minh bạch: trạng thái đơn luôn có icon + chữ, không chỉ dùng màu.
4. Ít nhiễu: bộ lọc gọn trong bottom sheet, hồ sơ kỹ năng dạng chip.
5. Luôn có đường lui: mọi lỗi đều có hành động phục hồi (Thử lại, gợi ý thay thế).

## Token (đề xuất, kiểm contrast bằng công cụ trước khi chốt)
| Nhóm | Giá trị |
|---|---|
| Primary | #1A3A6B (chữ trắng trên nền này) |
| Surface / container nhạt | #FFFFFF / #E8EEF7 |
| Text chính / phụ | #1F2933 / #4B5563 |
| Error | #B3261B |
| Accent (chỉ điểm nhấn, không dùng cho chữ) | #F27124 |
| Typography | Inter hoặc Roboto; body 14-16sp, tiêu đề 20-24sp |
| Spacing | 4 / 8 / 16 / 24 |
| Radius | 12 |
| Elevation | 0 / 1 / 3 |

## Ràng buộc accessibility
Contrast chữ thường ≥4.5:1, chữ lớn/điều khiển ≥3:1; tap target ≥48×48dp; chữ nội dung ≥14sp; kiểm tra khung 360 và 412dp; không dùng màu làm tín hiệu duy nhất.

## Trạng thái đơn (icon + chữ)
Chờ duyệt, Đã chấp nhận, Từ chối, Hết hiệu lực, Nhóm đã đủ.