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
  
