# Phần 5: Remote repository (GitHub or GitLab)
## 1. Giới thiệu về Remote repository
* Remote repository là kho lưu trữ mã nguồn từ xa, cho phép nhiều người cùng làm việc trên cùng một dự án thông qua mạng internet.
* Hai dịch vụ phổ biến để quản lý remote repository là GitHub và GitLab.
* Remote repository giúp đồng bộ hóa mã nguồn giữa các thành viên trong nhóm, theo dõi thay đổi và quản lý phiên bản hiệu quả.
## 2. Thêm remote và đẩy code
* Để thêm 1 remote repository, sử dụng lệnh: `git remote add <tên-remote> <url-repo>`
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần 1: Git và Github$ git add remote origin git@github.com:NguyenTuKien/typ-training-2025.git
```
* Để đẩy code từ local lên remote repository, sử dụng lệnh: `git push <tên-remote> <tên-nhánh>`
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần 1: Git và Github$ git push -u origin main
```
 - `-u`: Thiết lập nhánh upstream, giúp bạn có thể sử dụng lệnh `git push` và `git pull` mà không cần chỉ định tên remote và nhánh trong các lần sau.
* Để tải tất cả thông tin mới từ remote mà không tự động hợp nhất vào nhánh hiện tại, sử dụng lệnh: `git fetch <tên-remote>`
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần 1: Git và Github$ git fetch origin
```
 - Lệnh này sẽ tải về tất cả các thay đổi từ remote repository nhưng không áp dụng chúng vào nhánh hiện tại.
 - Những thay đổi (file, commit, ...) đó sẽ được lưu trữ trong `.git\objects` và tham chiếu được lưu trong `.git/FETCH_HEAD` , bạn có thể xem chúng hoặc hợp nhất chúng vào nhánh hiện tại sau.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần
 1: Git và Github$ git fetch
remote: Enumerating objects: 14, done.
remote: Counting objects: 100% (14/14), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 10 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (10/10), 2.16 KiB | 315.00 KiB/s, done.
From https://github.com/NguyenTuKien/typ-training-2025
   00def68..0cfdb2e  main       -> origin/main
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần
 1: Git và Github$ ls .git
ls: cannot access '.git': No such file or directory
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuần
 1: Git và Github$ cd ..                                                               
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1$ cd ..
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls .git
AUTO_MERGE  COMMIT_EDITMSG  description  HEAD   index  logs     ORIG_HEAD    refs
branches    config          FETCH_HEAD   hooks  info   objects  packed-refs
```
* Để tải và hợp nhất các thay đổi từ remote repository vào nhánh hiện tại, sử dụng lệnh: `git pull <tên-remote> <tên-nhánh>`
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ git pull origin main
From https://github.com/NguyenTuKien/typ-training-2025
 * branch            main       -> FETCH_HEAD
Updating 00def68..0cfdb2e
Fast-forward
 ...Nh\303\241nh (Branching) & h\341\273\243p nh\341\272\245t (Merging).md" | 6 +++---
 1 file changed, 3 insertions(+), 3 deletions(-)
```
 - Nếu có thay đổi local chưa commit, `git pull` sẽ thất bại. Khi đó ta cần `--no-rebase` hoặc `--rebase` để pull kiểu merge.
## 3. Mô hình làm việc nhóm (GitHub Flow)
* GitHub Flow là một mô hình làm việc nhóm đơn giản và hiệu quả, bao gồm các bước chính sau: 
  - **Bước 1:** Sao chép repository gốc về tài khoản cá nhân (`fork`).
  - **Bước 2:** Tải repo vừa `fork` về máy tính cá nhân (`clone`).
  - **Bước 3:** Tạo nhánh mới để làm việc trên tính năng hoặc sửa lỗi (`branch`).
  - **Bước 4:** Thực hiện các thay đổi và lưu lại (`commit`).
  - **Bước 5:** Đẩy nhánh lên repository cá nhân trên GitHub (`push`).
  - **Bước 6:** Tạo yêu cầu hợp nhất (`pull request`) để đề xuất thay đổi vào repository gốc.
  - **Bước 7:** Thảo luận và xem xét thay đổi, sau đó hợp nhất (`merge`) nếu được chấp nhận.
  - **Bước 8:** Cập nhật nhánh chính từ repository gốc để giữ cho nó luôn mới nhất (`pull`).
  - **Bước 9:** Xóa nhánh đã hoàn thành để giữ repository sạch sẽ (`delete branch`).
* Mô hình này giúp quản lý mã nguồn hiệu quả, giảm thiểu xung đột và tăng cường hợp tác trong nhóm phát triển.
## 4.Giải quyết xung đột (Merge Conflict)
[vid_1.webm](Image/vid_1.webm)