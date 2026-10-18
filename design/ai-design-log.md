# AI Design Log - TeamUp EXE (Google Stitch)

Quy ước: dán prompt NGUYÊN VĂN đã chạy, không sửa sau khi chạy. Muốn đổi thì tạo prompt mới. Ảnh đặt tên p1-*, r1-before-*, r1-after-* trong `screenshots/`.

## Prompt #1A: Generate (P1)
- Ngày giờ: ____
- Công cụ / chế độ: Google Stitch, Mobile
- Prompt nguyên văn:
> Design a mobile Android app (360dp width, Material 3) called "TeamUp EXE" for FPT University students to form teams for the EXE project course. Primary user: Khang, a 3rd-year software engineering student with backend skills, no team yet, using the phone one-handed between classes. Secondary user: Linh, a team leader who needs to recruit missing roles. Core tasks: sign in with an FPT email, build a skill profile, browse recruiting teams with filters, send a join request, track request status. Constraints: touch targets at least 48x48dp, body text at least 14sp, text contrast at least 4.5:1, never convey status by color alone (always icon plus text label), bottom navigation with 5 items (Home, Explore, My Team, Notifications, Profile), Vietnamese UI labels. Style: clean, friendly, academic, 12dp rounded corners, light theme, deep blue primary, orange used only for non-text highlights. Generate these screens: Login, Profile setup (skill chips, progress bar), Home (deadline countdown, my status, suggested teams), Explore teams (search, Filter button), Team detail (open roles, members, sticky Send request button).
- Ảnh output: screenshots/p1-login.png, p1-profile.png, p1-home.png, p1-explore.png, p1-team-detail.png
- Nhận xét ban đầu: ____

## Prompt #1B: Generate (P1)
- Ngày giờ: ____
- Prompt nguyên văn:
> Using the same design language, generate: My Team, Create team, Request management (tabs: Incoming, Sent; Accept/Reject), AI suggestions (cards with match score and 2-3 reasons, "Not suitable" button), Notifications.
- Ảnh output: screenshots/p1-my-team.png, p1-create-team.png, p1-requests.png, p1-ai.png, p1-notifications.png
- Nhận xét ban đầu: ____

## Critique (P2): tối thiểu 5 phát hiện, dựa trên output THẬT của Stitch
| # | Màn hình | Vấn đề | Căn cứ (Nielsen / A11y / Persona) | Đề xuất sửa |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

## Vòng 1: Điều hướng và cấu trúc
- Prompt nguyên văn (nháp, chỉnh theo critique rồi mới chạy): Keep the same app. Simplify navigation: move the primary "Send request" action to a sticky bottom button on Team detail, reduce filter chips on Explore into a single Filter button opening a bottom sheet, and show a progress indicator on Profile setup.
- Ảnh trước / sau: screenshots/r1-before-*.png, r1-after-*.png
- Critique / Quyết định (Accept, Modify, Reject) và lý do: ____
- Thay đổi tương ứng trong Figma: ____

## Vòng 2: Accessibility
- Prompt nguyên văn (nháp): Fix accessibility: all secondary text must reach 4.5:1 contrast, all tappable elements at least 48x48dp, body text at least 14sp, and request statuses (Pending, Accepted, Rejected, Full) must use icon plus text label, not color alone.
- Ảnh trước / sau: screenshots/r2-before-*.png, r2-after-*.png
- Critique / Quyết định và lý do: ____
- Thay đổi tương ứng trong Figma: ____

## Vòng 3: Trạng thái và lỗi
- Prompt nguyên văn (nháp): Add missing states: empty state for Explore with no results, loading skeleton for AI suggestions, error state with Retry for network failure, a "Team is full" state with similar-team suggestions, and a confirmation dialog before sending a request.
- Ảnh trước / sau: screenshots/r3-before-*.png, r3-after-*.png
- Critique / Quyết định và lý do: ____
- Thay đổi tương ứng trong Figma: ____