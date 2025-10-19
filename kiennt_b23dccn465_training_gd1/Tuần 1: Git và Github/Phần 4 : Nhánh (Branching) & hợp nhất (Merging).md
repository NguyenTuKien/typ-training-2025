#Phần 4 : Nhánh (Branching) & hợp nhất (Merging)
##1. Nhánh là gì và tại sao cần nhánh?
* **Nhánh (Branch)** là một phiên bản độc lập của mã nguồn trong hệ thống quản lý phiên bản Git. Mỗi nhánh cho phép bạn phát triển các tính năng mới, sửa lỗi hoặc thử nghiệm mà **không ảnh hưởng** đến mã nguồn chính (thường là nhánh "main" hoặc "master").
* Lý do cần sử dụng nhánh:
   - **Đảm bảo sự ổn đinh của mã nguồn chính:** Nhánh `main` (hoặc `master`) luôn được coi là 'sự thật'. Nó chứa mã nguồn đã được kiểm tra, ổn định và có thể đang chạy cho hàng ngàn người. Bằng cách phát triển trên các nhánh riêng biệt, bạn tránh làm hỏng mã nguồn chính.
   - **Phát triến song song:** Trong một dự án, có thể có nhiều người cùng làm các tính năng khác nhau. Nhánh cho phép mỗi người làm việc trên các tính năng riêng biệt mà không gây xung đột với nhau.
   - **Dễ dàng thử nghiệm:** Bạn có thể tạo nhánh để thử nghiệm các ý tưởng mới mà không lo lắng về việc làm hỏng mã nguồn chính. Nếu ý tưởng không thành công, bạn chỉ cần xóa nhánh đó mà không ảnh hưởng đến phần còn lại của dự án.
   - **Quản lý quy trình phát triển:** Nhánh giúp tổ chức và quản lý quá trình phát triển phần mềm, từ việc phát triển tính năng mới, sửa lỗi đến việc chuẩn bị các bản phát hành.
##2. Tạo và chuyển đổi giữa các nhánh
* Tạo nhánh mới:
   - Sử dụng lệnh `git branch <tên-nhánh>` để tạo một nhánh mới.
   - Ví dụ: `git branch feature-report` sẽ tạo một nhánh mới tên là `feature-report`.
* Chuyển đổi giữa các nhánh:
   - Sử dụng lệnh `git checkout <tên-nhánh>` để chuyển đổi sang nhánh khác.
   - Ví dụ: `git checkout feature-report` sẽ chuyển bạn sang nhánh `feature-report`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git branch feature-report
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git checkout feature-report
Switched to branch 'feature-report'
```
   - Nhưng vì `git checkout` có thể dùng cho nhiều mục đích khác nhau, nên từ Git phiên bản 2.23 trở đi, bạn có thể sử dụng lệnh `git switch <tên-nhánh>` để chuyển đổi giữa các nhánh, giúp làm rõ ý định của bạn hơn.
   - Ví dụ: `git switch main` sẽ chuyển bạn sang nhánh `main`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git switch main
M       "kiennt_b23dccn465_training_gd1/Tu\341\272\247n 1: Git v\303\240 Github/Ph\341\272\247n 4 : Nh\303\241nh (Branching) & h\341\273\243p nh\341\272\245t (Merging).md"
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 1 and 10 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)
```
* Tạo và chuyển đổi nhánh trong một lệnh:
   - Sử dụng lệnh `git checkout -b <tên-nhánh>` để tạo và chuyển đổi sang nhánh mới trong cùng một lệnh.
   - Ví dụ: `git checkout -b feature-login` sẽ tạo và chuyển bạn sang nhánh `feature-login`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git checkout -b feature-login
Switched to a new branch 'feature-login'
```
   - Hoặc sử dụng lệnh `git switch -c <tên-nhánh>` để tạo và chuyển đổi sang nhánh mới.
   - Ví dụ: `git switch -c feature-signup` sẽ tạo và chuyển bạn sang nhánh `feature-signup`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git switch -c feature-signup
Switched to a new branch 'feature-signup'
```
* Xóa một nhánh:
   - Sử dụng lệnh `git branch -d <tên-nhánh>` để xóa một nhánh đã được hợp nhất.
   - Ví dụ: `git branch -d feature-report` sẽ xóa nhánh `feature-report`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git branch -d feature-report
Deleted branch feature-report (was 9fceb02).
```
   - Sử dụng lệnh `git branch -D <tên-nhánh>` để xóa một nhánh bất kể nó đã được hợp nhất hay chưa.
   - Ví dụ: `git branch -D feature-login` sẽ xóa nhánh `feature-login`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git branch -D feature-login
Deleted branch feature-login (was 9fceb02).
```
* Liệt kê tất cả các nhánh:
   - Sử dụng lệnh `git branch` để liệt kê tất cả các nhánh trong repository.
   - Nhánh hiện tại sẽ được đánh dấu bằng dấu `*`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git branch
* main
  feature-report
  feature-login
  feature-signup
```
* Kiểm tra nhánh hiện tại:
   - Sử dụng lệnh `git branch --show-current` để hiển thị tên của nhánh hiện tại.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git branch --show-current
main
```
* **Lưu ý:** Trước khi chuyển đổi nhánh, hãy đảm bảo rằng bạn đã commit hoặc stash tất cả các thay đổi hiện tại để tránh mất dữ liệu.
##3. Hợp nhất nhánh (Merging)
* Hợp nhất nhánh là quá trình kết hợp các thay đổi từ một nhánh khác vào nhánh hiện tại. Điều này thường được thực hiện khi một tính năng hoặc sửa lỗi đã hoàn thành và cần được tích hợp vào nhánh chính (main hoặc master).
* Các bước để hợp nhất nhánh:
   - Chuyển sang nhánh mà bạn muốn hợp nhất các thay đổi vào.
   - Cập nhật nhanh hiện tại với các thay đổi mới nhất từ remote (đảm bảo bạn đang làm việc trên phiên bản mới nhất).
   - Sử dụng lệnh `git merge <tên-nhánh>` để hợp nhất nhánh.
* Ví dụ:
   - Giả sử bạn đang ở nhánh `main` và muốn hợp nhất các thay đổi từ nhánh `feature-report` vào `main`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git switch main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 1 and 10 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git pull origin main
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git merge feature-report
Updating 9fceb02..d958a6b
Fast-forward
 Phần 4 : Nhánh (Branching) & hợp nhất (Merging).md | 2 ++
 1 file changed, 2 insertions(+)
```
* Giải thích:
    - `git switch main`: Chuyển sang nhánh `main`.
    - `git pull origin main`: Cập nhật nhánh `main` với các thay đổi mới nhất từ remote.
    - `git merge feature-report`: Hợp nhất các thay đổi từ nhánh `feature-report` vào nhánh `main`.
* Xử lý xung đột khi hợp nhất:
   - Đôi khi, khi hợp nhất nhánh, có thể xảy ra xung đột nếu cùng một phần của mã nguồn đã được thay đổi trong cả hai nhánh.
   - Khi đó, Git sẽ thông báo về xung đột và yêu cầu bạn giải quyết chúng.
   - Để giải quyết xung đột:
      + Mở các tệp bị xung đột và tìm kiếm các dấu hiệu xung đột (thường được đánh dấu bằng `<<<<<<<`, `=======`, và `>>>>>>>`).
      + Chỉnh sửa mã nguồn để giữ lại những thay đổi bạn muốn và loại bỏ các dấu hiệu xung đột.
      + Sau khi giải quyết xung đột, sử dụng lệnh `git add <tệp>` để đánh dấu các tệp đã được giải quyết.
      + Cuối cùng, sử dụng lệnh `git commit` để hoàn tất quá trình hợp nhất.
* Ví dụ về xung đột:

