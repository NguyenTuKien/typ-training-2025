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
  + 
