# Phần 6: Công cụ và kỹ năng nâng cao
## 1. Tag và versioning
- Tag trong Git là một cách để đánh dấu các điểm quan trọng trong lịch sử commit, thường được sử dụng để đánh dấu các phiên bản phát hành (releases) của phần mềm.
- Có hai loại tag chính trong Git:
  - **Lightweight Tag**: Là một tham chiếu đơn giản đến một commit cụ thể, không có thông tin bổ sung như tác giả hay ngày tạo. Lightweight tag giống như một nhánh không thay đổi.
  - **Annotated Tag**: Là một đối tượng Git đầy đủ, chứa thông tin bổ sung như tác giả, ngày tạo và thông điệp mô tả. Annotated tag được lưu trữ trong cơ sở dữ liệu Git và có thể được ký số để đảm bảo tính toàn vẹn.
- Tạo tag:
  - **Lightweight Tag**: `git tag <tên-tag>`
  - **Annotated Tag**: `git tag -a <tên-tag> -m "thông điệp"`
- Xem danh sách tag: `git tag`
- Xem code hiện tại cách phiên bản gần nhất bao xa: `git describe --tags`
- Xem chi tiết một tag: `git show <tên-tag>`
- Đẩy tag lên remote repository: `git push origin <tên-tag>` hoặc `git push origin --tags` để đẩy tất cả các tag.
- Xóa tag: `git tag -d <tên-tag>` (xóa local), `git push origin --delete <tên-tag>` (xóa remote).
- Sử dụng tag giúp quản lý phiên bản hiệu quả, dễ dàng quay lại các phiên bản trước và theo dõi các điểm phát hành quan trọng trong lịch sử phát triển phần mềm.
## 2. Git stash
- Git stash là một tính năng trong Git cho phép bạn tạm thời lưu trữ các thay đổi chưa được commit trong Working Directory và Staging Area, để bạn có thể chuyển sang làm việc trên một nhánh khác mà không cần phải commit hoặc bỏ qua các thay đổi hiện tại.
- Các lệnh cơ bản với `stach`:
  + `git stach` : Cất tất cả các thay đổi của những file được theo dõi (Tracked File)
  + `git stach -u` : Cất tất cả thay dổi của những file mới (Untracked File)
  + `git stach list` : Xem tất cả các gói đã cất. Mỗi gói có 1 ID, ví dự : `stach{0}`, `stach{1}`
  + `git stach pop` : Lấy gói mới nhất (`stach{0}`) ra khỏi danh sách và áp dụng các thay đổi trở lại Working Directory
  + `git stach apply <stach_id>` : Áp dụng các thay đổi từ gói có ID cụ thể trở lại Working Directory mà không xóa gói khỏi danh sách. Nếu không có `stach_id`, lệnh sẽ áp dụng gói mới nhất.
  + `git stach drop <stach_id>` : Xóa gói có ID cụ thể khỏi danh sách mà không áp dụng các thay đổi. Nếu không có `stach_id`, lệnh sẽ xóa gói mới nhất.
  + `git stach clear` : Xóa tất cả các gói đã cất khỏi danh sách.
- Lưu ý: Khi sử dụng `git stach pop` hoặc `git stach apply`, nếu có xung đột giữa các thay đổi trong gói stash và các thay đổi hiện tại trong Working Directory, bạn sẽ cần phải giải quyết xung đột đó giống như khi thực hiện merge.
