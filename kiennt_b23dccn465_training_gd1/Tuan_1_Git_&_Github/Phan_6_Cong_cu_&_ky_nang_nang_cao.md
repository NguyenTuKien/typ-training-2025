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
- Sử dụng tag giúp quản lý phiên bản hiệu quả, dễ dàng quay lại các phiên bản trước và theo dõi các điểm phát hành quan rọng trong lịch sử phát triển phần mềm.
- Ví dụ : 
```shell
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git tag v0.0.1 #Tạo tag v0.0.1
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git tag #Xem tất cả tag
v0.0.1
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git add . 
warning: in the working copy of '.idea/misc.xml', LF will be replaced by CRLF the next time Git touches it
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git commit -m"Save"
[main 9911024] Save
 50 files changed, 28 insertions(+), 14 deletions(-)
 delete mode 100644 README.md
 ...
 rename kiennt_b23dccn465_training_gd1/{Tuan_1_Git&Github => Tuan_1_Git_&_Github}/Thuat_toan_SHA1.md (100%)
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git push 
info: please complete authentication in your browser...
Enumerating objects: 52, done.
Counting objects: 100% (52/52), done.
Delta compression using up to 12 threads
Compressing objects: 100% (47/47), done.
Writing objects: 100% (48/48), 2.72 MiB | 436.00 KiB/s, done.
Total 48 (delta 2), reused 33 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/NguyenTuKien/typ-training-2025.git
   c36f2f1..9911024  main -> main
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git tag -a v0.0.2 -m "Save" #Tạo tag v0.0.2 với thông điệp 
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git tag       
v0.0.1
v0.0.2
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git add .
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git commit -m"Save"
[main 5d76bd8] Save
 1 file changed, 6 insertions(+), 1 deletion(-)
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git describe #Xem code hiện tại các version gần nhất bao nhiêu commit
v0.0.2-1-g5d76bd8 #Commit ID hiện tại là g5d76bd8, cách phiên bản gần nhất 1 commit.
```
## 2. Git stash
- Git stash là một tính năng trong Git cho phép bạn tạm thời lưu trữ các thay đổi chưa được commit trong Working Directory và Staging Area, để bạn có thể chuyển sang làm việc trên một nhánh khác mà không cần phải commit hoặc bỏ qua các thay đổi hiện tại.
- Các lệnh cơ bản với `stash`:
  + `git stash` : Cất tất cả các thay đổi của những file được theo dõi (Tracked File)
  + `git stash -u` : Cất tất cả thay dổi của những file mới (Untracked File)
  + `git stash list` : Xem tất cả các gói đã cất. Mỗi gói có 1 ID, ví dự : `stash{0}`, `stash{1}`
  + `git stash pop` : Lấy gói mới nhất (`stash{0}`) ra khỏi danh sách và áp dụng các thay đổi trở lại Working Directory
  + `git stash apply <stash_id>` : Áp dụng các thay đổi từ gói có ID cụ thể trở lại Working Directory mà không xóa gói khỏi danh sách. Nếu không có `stash_id`, lệnh sẽ áp dụng gói mới nhất.
  + `git stash drop <stash_id>` : Xóa gói có ID cụ thể khỏi danh sách mà không áp dụng các thay đổi. Nếu không có `stash_id`, lệnh sẽ xóa gói mới nhất.
  + `git stash clear` : Xóa tất cả các gói đã cất khỏi danh sách.
- Lưu ý: Khi sử dụng `git stash pop` hoặc `git stash apply`, nếu có xung đột giữa các thay đổi trong gói stash và các thay đổi hiện tại trong Working Directory, bạn sẽ cần phải giải quyết xung đột đó giống như khi thực hiện merge.
- Ví dụ:
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git status
On branch main
Your branch is up to date with 'origin/main'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/Thuat_toan_SHA1.md
    
no changes added to commit (use "git add" and/or "git commit -a")
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git stash
Saved working directory and index state WIP on main: 9911024 Save
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git switch dev
Switched to branch 'dev'
```
    + Sau khi chuyển nhánh, bạn có thể làm việc trên nhánh `dev` mà không bị ảnh hưởng bởi các thay đổi chưa commit trên nhánh `main`.
    + Bây giờ, nếu bạn muốn quay lại nhánh `main` và áp dụng các thay đổi đã stash, bạn có thể làm như sau:
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git switch main
Switched to branch 'main'
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git stash pop
On branch main
Your branch is up to date with 'origin/main'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/Thuat_toan_SHA1.md
    
no changes added to commit (use "git add" and/or "git commit -a")
```
## 3. Rebase và squash
- Git rebase là một kỹ thuật trong Git được sử dụng để di chuyển hoặc kết hợp một chuỗi các commit từ một nhánh này sang một nhánh khác. Rebase giúp giữ cho lịch sử commit sạch sẽ và tuyến tính hơn so với việc sử dụng merge.
- Cách sử dụng Git rebase:
    + `git checkout <nhánh-đích>`: Chuyển sang nhánh mà bạn muốn áp dụng các commit.
    + `git rebase <nhánh-nguồn>`: Áp dụng các commit từ nhánh nguồn lên nhánh đích.
- Khi sử dụng rebase, Git sẽ "chơi lại" các commit từ nhánh nguồn trên đỉnh của nhánh đích, tạo ra một lịch sử commit mới.
- Tuy nhiên, nếu có xung đột giữa các commit (thường là giữa commit cuối của nhánh rebase với commit đầu của nhánh được rebase), Git sẽ tạm dừng quá trình rebase và yêu cầu bạn giải quyết xung đột trước khi tiếp tục.
- Squash là một kỹ thuật trong Git được sử dụng để kết hợp nhiều commit thành một commit duy nhất. Điều này thường được sử dụng để làm sạch lịch sử commit trước khi hợp nhất (merge) một nhánh vào nhánh chính.
- Cách sử dụng Git squash:
    + Sử dụng lệnh `git rebase -i <commit-hash>` để bắt đầu một rebase tương tác, trong đó `<commit-hash>` là mã hash của commit trước commit đầu tiên mà bạn muốn squash.
    + Trong trình soạn thảo rebase, thay đổi từ `pick` thành `squash` (hoặc `s`) cho các commit mà bạn muốn kết hợp vào commit trước đó.
    + Lưu và đóng trình soạn thảo. Git sẽ yêu cầu bạn chỉnh sửa thông điệp commit cho commit mới được tạo ra từ việc squash.
    + Lưu và đóng trình soạn thảo để hoàn tất quá trình squash.
- Lưu ý: Khi sử dụng rebase và squash, đặc biệt là trên các nhánh đã được chia sẻ với người khác, hãy cẩn thận vì chúng có thể thay đổi lịch sử commit và gây ra xung đột nếu không được xử lý đúng cách.
## 4. Git alias & log formatting
- Git alias là một cách để tạo các tên ngắn gọn hoặc tùy chỉnh cho các lệnh Git dài hoặc phức tạp, giúp tiết kiệm thời gian và công sức khi làm việc với Git.
- Cách tạo Git alias:
    + Sử dụng lệnh `git config --global alias.<tên-alias> '<lệnh-git>'` để tạo alias toàn cục (áp dụng cho tất cả các repository trên máy tính của bạn).
    + Ví dụ:
```shell
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git config --global alias.co checkout
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git config --global alias.br branch
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git config --global alias.ci commit
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git config --global alias.st status
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git co main
Switched to branch 'main'
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git br
* main
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git ci -m"Test alias"
[main 1f4e2b3] Test alias
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git st
On branch main
Your branch is up to date with 'origin/main'. 
```
- Git log formatting là cách tùy chỉnh cách hiển thị lịch sử commit khi sử dụng lệnh `git log`, giúp bạn dễ dàng đọc và hiểu các commit trong repository.
- Cách sử dụng Git log formatting:
    + Sử dụng các tùy chọn của lệnh `git log` để thay đổi định dạng hiển thị.
    + Ví dụ:
```shell
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git config --global alias.lg "log --oneline --graph --all --decorate"
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git lg
* b1a2c3d (HEAD -> feature-A) Merge pull request #12
|\
| * 4e5f6g7 (origin/main, main) Add new feature
| |
* | d7e8f9g Fix bug login
|/
* a0b1c2d (v1.0) Initial commit
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git log --graph --all --pretty="format:%C(yellow)%h%C(reset) - %C(cyan)(%ar)%C(reset) - %C(blue)%an%C(reset) - %s %C(auto,red)%d%C(reset)"
* b1a2c3d - (2 days ago) - NguyenTuKien - Merge pull request #12  (HEAD -> feature-A)
|\
| * 4e5f6g7 - (3 days ago) - Mot Nguoi Khac - Add new feature  (origin/main, main)
| |
* | d7e8f9g - (3 days ago) - NguyenTuKien - Fix bug login
|/
* a0b1c2d - (5 days ago) - NguyenTuKien - Initial commit  (tag: v1.0)
```
- Các placeholder hữu ích:
  * `%h`: Mã hash rút gọn (ví dụ: `b1a2c3d`)
  * `%H`: Mã hash đầy đủ
  * `%s`: Tiêu đề/thông điệp commit (Subject)
  * `%an`: Tên tác giả (Author Name)
  * `%ar`: Ngày của tác giả, tương đối (Author Date, Relative) (ví dụ: "2S days ago")
  * `%ad`: Ngày của tác giả, tuyệt đối (Author Date) (ví dụ: "2025-10-21")
  * `%d`: "Decorations" (tên nhánh, tên tag) (ví dụ: `(HEAD -> main, tag: v1.0)`)
  * `%C(...)`: Bắt đầu tô màu (ví dụ: `%C(yellow)`)
  * `%C(reset)`: Tắt tô màu
  * `%C(auto)`: Tự động tô màu (được khuyên dùng)
## 5. Git reflog và khôi phục commit bị mất
- `git reflog` là một lệnh trong Git cho phép bạn xem lịch sử các thay đổi của tham chiếu (references) trong repository, bao gồm cả các commit đã bị xóa hoặc thay đổi. Reflog ghi lại mọi thay đổi đối với HEAD và các tham chiếu khác, giúp bạn có thể khôi phục các commit bị mất hoặc quay lại trạng thái trước đó của repository.
- Nó ghi lại những `commit`, `checkout`, `reset`(kể cả `reset --hard` làm mất commit), `rebase`, `merge`... mà bạn đã thực hiện trong repository.
- Reflog chỉ theo dõi local repo, nên nó chỉ lưu ở local mà không được push lên remote.
- Bằng cách xem reflog, bạn có thể khôi phục lại những commit mà tưởng như đã bị xóa.
- Ví dụ:
```shell
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git reflog
a1b2c3d (HEAD -> feature) HEAD@{0}: reset: moving to HEAD~3  <-- À HA! Đây là lúc bạn reset!
d4e5f6g HEAD@{1}: commit: Hoan thanh tinh nang C         <-- Đây là commit C
c7d8e9f HEAD@{2}: commit: Fix bug B
b0a1b2c HEAD@{3}: commit: Them tinh nang A
a1b2c3d HEAD@{4}: checkout: moving from main to feature
PS C:\Users\Admin\OneDrive\Documents\typ-training-2025> git reset --hard d4e5f6g
HEAD is now at d4e5f6g Add new feature
```
