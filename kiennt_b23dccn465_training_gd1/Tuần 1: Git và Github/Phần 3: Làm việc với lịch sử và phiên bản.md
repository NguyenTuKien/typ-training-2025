## Phần 3 : Làm việc với lịch sử và phiên bản    
1. **Cách xem lịch sử và phiên bản commit.**
* Xem lịch sử commit:
   - `git log`: Hiển thị danh sách các commit trong repository, bao gồm mã hash, tác giả, ngày tháng và thông điệp commit.
  ![img_21.png](Image/img_21.png)
   - `git log --oneline`: Hiển thị lịch sử commit dưới dạng một dòng cho mỗi commit, giúp dễ dàng xem tổng quan.
  ![img_22.png](Image/img_22.png)
   - `git log --graph --oneline --all`: Hiển thị lịch sử commit dưới dạng đồ thị, giúp hình dung các nhánh và merge.
  ![img_23.png](Image/img_23.png)
* Xem chi tiết một commit cụ thể:
    - `git show <commit-hash>`: Hiển thị chi tiết về một commit
    - `git diff <commit-hash1> <commit-hash2>`: So sánh sự khác biệt giữa hai commit.