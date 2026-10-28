# AI Design Log - TeamUp EXE (Google Stitch)

Quy ước: dán prompt NGUYÊN VĂN đã chạy, không sửa sau khi chạy. Muốn đổi thì tạo prompt mới. Ảnh đặt tên `p1-*`, `r1-before-*`, `r1-after-*` trong `screenshots/`.
Dòng có nhãn **[Kiểm tra]** hoặc **[Điền]** là chỗ cần đối chiếu lại trong Stitch hoặc điền số liệu thật trước khi nộp.

## Prompt #1A: Generate (P1)
- Ngày giờ: [Điền] ____
- Người thực hiện: SE183979
- Công cụ / chế độ: Google Stitch, Mobile
- Prompt nguyên văn:
> Design a mobile Android app (360dp width, Material 3) called "TeamUp EXE" for FPT University students to form teams for the EXE project course. Primary user: Khang, a 3rd-year software engineering student with backend skills, no team yet, using the phone one-handed between classes. Secondary user: Linh, a team leader who needs to recruit missing roles. Core tasks: sign in with an FPT email, build a skill profile, browse recruiting teams with filters, send a join request, track request status. Constraints: touch targets at least 48x48dp, body text at least 14sp, text contrast at least 4.5:1, never convey status by color alone (always icon plus text label), bottom navigation with 5 items (Home, Explore, My Team, Notifications, Profile), Vietnamese UI labels. Style: clean, friendly, academic, 12dp rounded corners, light theme, deep blue primary, orange used only for non-text highlights. Generate these screens: Login, Profile setup (skill chips, progress bar), Home (deadline countdown, my status, suggested teams), Explore teams (search, Filter button), Team detail (open roles, members, sticky Send request button).
- Ảnh output: screenshots/p1-login.png, p1-profile.png, p1-home.png, p1-explore.png, p1-team-detail.png
- Nhận xét ban đầu: Stitch sinh đủ 5 màn, nhãn tiếng Việt, có bottom navigation 5 mục. Tên màn do Stitch đặt ban đầu không khớp nội dung nên đã đổi lại tên khi lưu ảnh. Home có nhiều thông tin; Explore dùng hàng chip lọc thay vì một nút Filter; Team detail và Profile setup cần cuộn dài. [Kiểm tra] thanh tiến độ ở Profile setup và nút "Gửi đơn" cố định ở Team detail.

## Prompt #1B: Generate (P1)
- Ngày giờ: [Điền] ____
- Người thực hiện: SE183979
- Công cụ / chế độ: Google Stitch, Mobile (cùng dự án với #1A)
- Prompt nguyên văn:
> Using the same design language, generate: My Team, Create team, Request management (tabs: Incoming, Sent; Accept/Reject), AI suggestions (cards with match score and 2-3 reasons, "Not suitable" button), Notifications.
- Ảnh output: screenshots/p1-my-team.png, p1-create-team.png, p1-requests.png, p1-ai.png, p1-notifications.png (màn dài: thêm p1-create-team-2.png, p1-requests-2.png)
- Nhận xét ban đầu: Stitch sinh đủ 5 màn, giữ được phong cách xanh đậm. Gợi ý AI có điểm phù hợp, lý do và nút "Không phù hợp" đúng yêu cầu, nhưng hiện cả tên thuật toán. Thông báo thêm mục tùy biến email/Telegram ngoài phạm vi. Tạo nhóm là form dài nhiều mục.

## Critique (P2): tối thiểu 5 phát hiện, dựa trên output THẬT của Stitch
| # | Màn hình | Vấn đề | Căn cứ (Nielsen / A11y / Persona) | Đề xuất sửa |
|---|---|---|---|---|
| 1 | Home | Quá dày thông tin: cảnh báo hạn chốt, trạng thái nhóm, banner tuyển, 2 thẻ gợi ý, mẹo giảng viên xuất hiện cùng lúc | Nielsen: thẩm mỹ tối giản. Persona: Khang dùng một tay, lướt nhanh giữa tiết học | Giữ cảnh báo deadline, trạng thái, tối đa 2 thẻ gợi ý; bỏ hoặc gộp banner và mẹo |
| 2 | Home | Dòng "Cần tuyển" dùng chữ cam/nâu trên nền cam nhạt, trái ràng buộc "cam chỉ cho điểm nhấn không phải chữ". [Điền] tỷ lệ contrast đo bằng WebAIM: ____:1 | A11y: contrast chữ thường ≥4.5:1 | Đổi chữ sang xanh đậm hoặc xám đậm, giữ nền cam nhạt |
| 3 | Explore | Thanh lọc là một hàng chip dài chiếm chỗ, trái yêu cầu một nút Filter | Nielsen: thẩm mỹ tối giản, nhận biết thay vì nhớ | Gom thành nút Lọc mở bottom sheet, hiện số bộ lọc đang bật |
| 4 | Team detail | [Kiểm tra] Chưa thấy nút "Gửi đơn" cố định ở đáy; màn dài, hành động chính nằm xa tầm ngón cái | Nielsen: kiểm soát và tự do. Persona: gửi đơn ≤4 chạm từ Home, dùng một tay | Thêm nút sticky "Gửi đơn" ở đáy màn hình |
| 5 | Gợi ý AI | Hiện tên thuật toán kỹ thuật ("Matchmaker v2.4") và khối tùy chỉnh tiêu chí; người dùng không cần biết | Nielsen: khớp giữa hệ thống và thế giới thực | Bỏ thuật ngữ, giữ điểm phù hợp, 2-3 lý do và nút "Không phù hợp" |
| 6 | Thông báo | Có mục tùy biến thông báo qua email và Bot Telegram, ngoài phạm vi sản phẩm Lab 2 | Nielsen: thẩm mỹ tối giản; phạm vi đề tài | Bỏ mục này |
| 7 | Tạo nhóm | Form dài 4 mục, nhiều trường, phải cuộn nhiều và nhập liệu dài | Persona: dùng một tay giữa tiết học. Nielsen: phòng lỗi | Chia thành các bước ngắn hoặc rút gọn trường bắt buộc, thêm thanh tiến độ |
| 8 | Nhóm của tôi | [Kiểm tra] Chưa thấy nút Chốt nhóm và Rời nhóm | Đối chiếu Flow 2 (dialog Chốt nhóm) | Thêm nút và dialog xác nhận trước khi chốt/rời |

Ghi chú: dòng 4 và 8 xóa nếu khi cuộn xuống thấy Stitch đã có sẵn nút. Nếu bỏ thì cần còn ≥5 dòng.

## Vòng 1: Điều hướng và cấu trúc
- Mục tiêu: giảm quá tải, đưa hành động chính vào tầm ngón cái (phát hiện 1, 3, 4, 7).
- Prompt nguyên văn (nháp, chỉnh theo critique rồi mới chạy): Keep the same app and visual style. Simplify structure: on Home keep only the deadline countdown, my team status and at most 2 suggested teams; on Explore replace the row of filter chips with a single Filter button that opens a bottom sheet; on Team detail add a sticky bottom "Gửi đơn" button; on Create team split the long form into short steps with a progress indicator.
- Ngày giờ chạy: [Điền] ____
- Ảnh trước / sau: screenshots/r1-before-home.png, r1-after-home.png, r1-before-explore.png, r1-after-explore.png, r1-before-team-detail.png, r1-after-team-detail.png
- Critique sau khi xem kết quả: [Điền]
- Quyết định (Accept / Modify / Reject) và lý do: [Điền] Gợi ý: Modify cho bộ lọc (chip → bottom sheet) vì persona dùng một tay.
- Thay đổi tương ứng trong Figma: [Điền] page 03 Final UI, frame S3, S4, S5.

## Vòng 2: Accessibility
- Mục tiêu: đạt contrast, cỡ chữ, tap target và không chỉ dùng màu (phát hiện 2).
- Prompt nguyên văn (nháp): Fix accessibility: all secondary text must reach 4.5:1 contrast, no orange text on light backgrounds, all tappable elements at least 48x48dp, body text at least 14sp, and request statuses (Pending, Accepted, Rejected, Full) must use icon plus text label, not color alone.
- Ngày giờ chạy: [Điền] ____
- Ảnh trước / sau: screenshots/r2-before-*.png, r2-after-*.png
- Critique sau khi xem kết quả: [Điền]
- Quyết định và lý do: [Điền] Gợi ý: Reject chữ cam trên nền sáng vì contrast thấp.
- Thay đổi tương ứng trong Figma: [Điền] Variables màu trong page 04, bằng chứng đo trong design-decisions.md.

## Vòng 3: Trạng thái và lỗi
- Mục tiêu: bổ sung empty, loading, error và dialog xác nhận (phát hiện 5, 6, 8 và các nhánh lỗi của 3 flow).
- Prompt nguyên văn (nháp): Add missing states: empty state for Explore with no results, loading skeleton for AI suggestions, error state with Retry for network failure, a "Team is full" state with similar-team suggestions, a confirmation dialog before sending a request, and a confirm dialog for locking or leaving a team. Remove the technical algorithm name from AI suggestions and remove the email/Telegram notification settings.
- Ngày giờ chạy: [Điền] ____
- Ảnh trước / sau: screenshots/r3-before-*.png, r3-after-*.png
- Critique sau khi xem kết quả: [Điền]
- Quyết định và lý do: [Điền] Gợi ý: Reject phần Telegram/email vì ngoài phạm vi.
- Thay đổi tương ứng trong Figma: [Điền] Component Dialog, Loading, Empty, Error trong page 05; frame trạng thái trong page 03; nhánh lỗi trong prototype page 06.git 