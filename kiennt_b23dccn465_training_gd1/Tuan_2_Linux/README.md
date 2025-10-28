# Phần 1 : Giới thiệu tổng quan về Linux
## 1. Linux là gì?
* Linux là nhân (kernel) của một hệ điều hành mã nguồn mở, được phát triển lần đầu bởi Linus Torvalds vào năm 1991 bằng ngôn ngữ lập trình C. 
* Nhân là thành phần cốt lõi, hoạt động như cầu nối trung gian giữa phần cứng và phần mềm.
* Tuy nhiên, khi nói về "Linux" trong ngữ cảnh phổ biến, chúng ta thường đề cập đến các hệ điều hành dựa trên nhân Linux, được gọi là các bản phân phối Linux (Linux distributions).
## 2. Lịch sử phát triển của Linux
* Người khởi xướng: Linus Torvalds, một sinh viên khoa học máy tính người Phần Lan.
* Thời điểm: Bắt đầu vào năm 1991.
* Động lực: Linus muốn tạo ra một nhân hệ điều hành miễn phí, giống UNIX, có thể chạy trên máy tính cá nhân (PC) của mình.
* Phát triển ban đầu: Ban đầu, nó chỉ là một dự án "sở thích" cá nhân, không có ý định trở nên lớn mạnh hay chuyên nghiệp.
* Sự kết hợp quan trọng (GNU/Linux): Dự án của Linus chỉ tạo ra nhân (kernel). Để trở thành một hệ điều hành hoàn chỉnh, nó đã được kết hợp với các công cụ phần mềm miễn phí từ Dự án GNU (của Richard Stallman), vốn đang thiếu một hạt nhân.
* Kết quả: Sự kết hợp giữa nhân Linux và các công cụ GNU đã tạo ra một hệ điều hành hoàn chỉnh, miễn phí và mã nguồn mở.
* Linh vật: Linh vật của Linux là một con chim cánh cụt tên là Tux.
## 3. Linux kernel vs Linux distribution
| Tiêu chí | Linux Kernel (Nhân Linux) | Linux Distribution (Bản phân phối - Đại diện: Ubuntu) |
| :--- | :--- | :--- |
| **Định nghĩa** | Là **lõi (trái tim)** của hệ điều hành. Đây là thành phần duy nhất mà Linus Torvalds khởi xướng. | Là một **hệ điều hành hoàn chỉnh**, có thể sử dụng được, được xây dựng *bao quanh* nhân Linux. |
| **Phép so sánh** | **Động cơ của một chiếc xe hơi** 🚗. Cực kỳ quan trọng nhưng tự nó không thể lái đi được. | **Một chiếc xe hơi hoàn chỉnh**. Bao gồm động cơ (kernel), khung xe, bánh xe, vô lăng (GUI), và hệ thống nhiên liệu (công cụ). |
| **Thành phần bao gồm**| Chỉ bao gồm nhân: Quản lý tiến trình, quản lý bộ nhớ, driver phần cứng, quản lý file system, mạng. | **Kernel** + **Mọi thứ khác**: Môi trường Desktop (ví dụ: **GNOME**), trình quản lý gói (`apt`), trình bao (`bash`), các công cụ GNU, và hàng ngàn ứng dụng (Firefox, LibreOffice...). |
| **Tương tác người dùng**| Người dùng **không** tương tác trực tiếp. Các chương trình tương tác với nó thông qua các lời gọi hệ thống (system calls). | Người dùng **tương tác trực tiếp** thông qua Giao diện Đồ họa Người dùng (GUI) hoặc Giao diện Dòng lệnh (CLI Terminal). |
| **Mục đích** | Cung cấp một lớp trừu tượng để phần mềm có thể giao tiếp với phần cứng một cách ổn định và an toàn. | Cung cấp một môi trường làm việc/máy chủ hoàn chỉnh, thân thiện, dễ cài đặt và sử dụng cho người dùng cuối. |
| **Người phát triển** | Linus Torvalds và cộng đồng phát triển kernel toàn cầu (hàng ngàn lập trình viên từ nhiều công ty). | Công ty **Canonical** (tổ chức đứng sau Ubuntu) và cộng đồng Ubuntu. |
| **Trình quản lý gói** | **Không có**. Nó là một thành phần phần mềm đơn lẻ (mặc dù được module hóa). | **Có (ví dụ: `apt`, `dpkg`, `snap`)**. Đây là công cụ cốt lõi để cài đặt, cập nhật và quản lý phần mềm. |
| **Giao diện đồ họa (GUI)** | **Không có**. Nó hoạt động ở mức độ thấp, không liên quan đến hiển thị đồ họa. | **Có (mặc định là GNOME)**. Đây là một phần quan trọng của trải nghiệm desktop Ubuntu. (Phiên bản server có thể không cài GUI). |
| **Ví dụ phiên bản** | `Linux kernel 6.5.0` | `Ubuntu 22.04 LTS` (Bản phân phối này sẽ "đóng gói" một phiên bản kernel cụ thể bên trong nó, ví dụ: kernel 5.15). |
| **Quy trình cập nhật** | Kernel được cập nhật liên tục bởi cộng đồng. Người dùng nâng cao có thể tự biên dịch và cài đặt kernel mới nhất. | Canonical kiểm tra, vá lỗi, và "đóng gói" một phiên bản kernel ổn định, sau đó phát hành nó dưới dạng bản cập nhật hệ thống an toàn qua `apt`. |
## 4. Ứng dụng của Linux
* Server (Máy chủ) : Linux thống trị tuyệt đối do tính ổn định, bảo mật (phân quền, SELinux), hiệu suất cao (chạy Nginx, Apache, MySQL) và miễn phí.
* Cloud (Điện toán đám mây) : Linux là gỗ rễ của ảo hóa (KVM) và containerization (Docker, Kubernetes).
* Devops : Linux là hệ điều hành mặc định nhờ khả năng tự động hóa mạnh mẽ (Bash scripting), hệ sinh thái công cụ phong phú (Ansible, Terraform) và tạo môi trường đồng nhất (dev/prod).
* AI & ML : Linux là lựa chọn hàng đầu nhờ hỗ trợ drive GPU (NVIDIA CUDA) tốt nhất, các framework (TensorFlow, PyTorch) được tối ưu cho Linux.
* Lập trình hệ thống : Linux cung cấp môi trường phát triển mạnh mẽ (GCC, GDB), truy cập trực tiếp vào phần cứng và tài liệu phong phú.
## 5. Sự khác biệt giữa Linux và Windows/MacOS
| Tiêu chí | Linux | Windows | macOS |
| :--- | :--- | :--- | :--- |
| **Chi phí & Giấy phép** | **Miễn phí hoàn toàn**. Giấy phép Mã nguồn mở (chủ yếu là GPL). | **Phải trả phí bản quyền**. Thường được cài đặt sẵn khi mua máy tính mới. | **Miễn phí** (nhưng *bắt buộc* phải mua phần cứng của Apple). |
| **Mã nguồn** | **Mã nguồn mở (Open Source)**. Bất kỳ ai cũng có thể xem, sửa đổi và phân phối. | **Mã nguồn đóng (Closed Source)**. Thuộc sở hữu độc quyền của Microsoft. | **Mã nguồn đóng**. Thuộc sở hữu của Apple (nhưng dựa trên nền tảng UNIX mã nguồn mở là Darwin). |
| **Nhà phát triển** | Được phát triển bởi một **cộng đồng toàn cầu** (dẫn đầu bởi Linus Torvalds và nhiều công ty). | Được phát triển và sở hữu bởi **Microsoft**. | Được phát triển và sở hữu bởi **Apple**. |
| **Phần cứng** | **Hỗ trợ đa dạng nhất**. Chạy trên gần như mọi thứ (PC, máy chủ, điện thoại, IoT...). | Chủ yếu chạy trên kiến trúc **PC (x86, ARM)**. Hỗ trợ phần cứng rộng rãi. | **Hệ sinh thái đóng**. Chỉ chạy chính thức trên phần cứng của Apple (Macs). |
| **Tùy biến Giao diện** | **Tùy biến cực cao**. Bạn có thể thay đổi mọi thứ, chọn nhiều Môi trường Desktop (GNOME, KDE, XFCE...). | **Tùsao-i-T.T.i.T.a.** Giao diện (Start Menu, Taskbar) tương đối cố định. | **Rất ít tùy biến**. Giao diện (Dock, Menu Bar) đồng nhất và "bóng bẩy" nhưng không linh hoạt. |
| **Quản lý Phần mềm** | **Trình quản lý gói (Package Manager)** là chính (ví dụ: `apt` của Ubuntu, `dnf` của Fedora). Rất nhanh và tập trung. | **Tệp `.exe` / `.msi`** (tải từ web) và **Microsoft Store**. Phân mảnh hơn. | **App Store** và tệp **`.dmg`** (kéo-thả). Hệ sinh thái được kiểm soát chặt chẽ. |
| **Dòng lệnh (Terminal)** | **Rất mạnh mẽ (Bash/Zsh)**. Là một phần cốt lõi, không thể thiếu của hệ thống. | Yếu (CMD), nhưng đã cải tiến nhiều với **PowerShell** và **WSL** (chạy Linux bên trong Windows). | **Rất mạnh mẽ (Zsh)**. Tương tự Linux vì được xây dựng trên nền tảng **UNIX**. |
| **Bảo mật** | **Rất an toàn**. Cấu trúc phân quyền chặt chẽ và mã nguồn mở giúp vá lỗi nhanh. Ít là mục tiêu của virus. | **Mục tiêu lớn nhất** của virus/malware (do thị phần lớn). Đã cải thiện nhiều với Windows Defender. | **Rất an toàn**. Dựa trên UNIX và hệ sinh thái khép kín giúp giảm thiểu rủi ro. |
| **Đối tượng chính** | **Máy chủ (Server)**, **DevOps**, Lập trình viên, Người dùng kỹ thuật, Hệ thống nhúng. | **Người dùng phổ thông**, **Văn phòng (Doanh nghiệp)**, **Game thủ PC**. | **Người dùng sáng tạo** (Design, Video, Nhạc), Lập trình viên, Người dùng thích sự đơn giản và đồng bộ. |
| **Điểm mạnh chính** | Ổn định, Miễn phí, Linh hoạt, Bảo mật, Tự động hóa. | Hỗ trợ phần cứng/phần mềm rộng nhất, Gaming, Dễ sử dụng (phổ thông). | Trải nghiệm người dùng mượt mà, "Bóng bẩy", Hệ sinh thái đồng bộ (iPhone, iPad), Sáng tạo. |
## 6. Kiến trúc Hệ thống Linux
* **Tầng Ứng dụng (Application Layer) :**
  * Bao gồm tất cả các ứng dụng và phần mềm mà người dùng tương tác trực tiếp, như trình duyệt web, trình soạn thảo văn bản, IDE, v.v.
  * Các ứng dụng không được phép "nói chuyện" trực tiếp với phần cứng.
* **Tầng Shell (Giao diện người dùng) :**
  * Đây là "bảng điều khiển" mà người dùng sử dụng để tương tác với hệ thống.
  * Nhiệm vụ : Nhận lệnh từ người dùng (từ cửa sổ terminal hoặc GUI) và dịch chúng thành các yêu cầu mà Kernel có thể hiểu được.
  * Ví dụ : `bash`, `zsh`, ...
* **Tầng Kernel (Nhân hệ điều hành) :**
  * Là "Bộ não" và "trái tim" của hệ thống Linux.
  * Nó nằm giữa phần cứng và phần mềm.
  * Nhiệm vụ chính:
    * Quản lý phần cứng : Giao tiếp với CPU, bộ nhớ, thiết bị lưu trữ, thiết bị mạng thông qua các driver.
    * Quản lý bộ nhớ : Cấp RAM cho các ứng dụng.
    * Quản lý tiến trình : Quyết định xem ứng dụng nào được chạy, khi nào và trong bao lâu.
    * System Calls : Cung cấp giao diện an toàn (API) để tầng ứng dụng yêu cầu tài nguyên.
## 7. Quá trình khởi động Linux
* **BIOS/UEFI(Fireware)**
  * Đây là chương trình đầu tiên chạy, được lưu trong chip trên bo mạch chủ.
  * Nó thực hiện **POST (Post-On Self Test)** để kiểm tra phần cứng cơ bản (RAM, CPU, thiết bị lưu trữ).
  * Nhiệm vụ chính : Tìm 1 thiết bị có khả năng khởi động (như ổ cứng, USB).
* **Bootloader (Trình tải khởi động)**
  * Sau khi BIOS/UEFI xác định thiết bị khởi động, nó sẽ chuyển quyền điều khiển cho Bootloader.
  * Nhiệm vụ chính : Tải nhân Linux (kernel) vào bộ nhớ và chuyển quyền điều khiển cho nó.
  * Ví dụ phổ biến : GRUB (Grand Unified Bootloader).
* **Kernel (Nhân hệ điều hành)**
  * Khi được Bootloader tải vào bộ nhớ, nhân Linux giải nén và khởi động.
  * Nó khởi tạo các trình điều khiển (drivers) thiết yếu và tải `initramfs` (hệ thống file tạm thời trong RAM) để chuẩn bị cho việc gắn (mount) vào ổ đĩa thật.
* **Init System (Hệ thống khởi tạo)**
  * Kernel khởi chạy chương tiến trình (process) đầu tiên của hệ thống, gọi là `init`.
  * Trong hầu hết hệ thống Linux hiện đại, `init` thường là `systemd`.
  * `systemd` có PID (Process ID) = 1. Nó là "bố già" của tất cả các tiến trình khác.
  * Nhiệm vụ chính : Khởi động các dịch vụ hệ thống (networking, logging, display manager) và chuẩn bị môi trường người dùng.
* **Login Prompt (Giao diện đăng nhập)**
  * Sau khi tất cả dịch vụ cần thiết được khởi động, hệ thống sẽ hiển thị giao diện đăng nhập.
  * Người dùng có thể đăng nhập qua giao diện đồ họa (GUI) hoặc dòng lệnh (CLI Terminal).
* **User Session (Phiên làm việc người dùng)**
  * Sau khi đăng nhập, hệ thống khởi chạy môi trường desktop (như GNOME, KDE) hoặc shell (như bash, zsh) để người dùng tương tác với hệ thống.
  * Người dùng có thể bắt đầu sử dụng các ứng dụng và dịch vụ trên hệ thống Linux.
## 8. Các thư mục hệ thống chính trong Linux
```shell
ngtukien@NgTuKien:/$ ls 
bin                boot   dev  home  lib64              lost+found  mnt  proc  run   sbin.usr-is-merged  srv       sys  usr
bin.usr-is-merged  cdrom  etc  lib   lib.usr-is-merged  media       opt  root  sbin  snap                swap.img  tmp  var
```
* `/bin` (Binaries): Chứa các lệnh (chương trình) cơ bản cần thiết cho hệ thống và người dùng, như `ls`, `cp`, `mv`. (Trên hệ thống của bạn, đây có thể là một liên kết tượng trưng đến `/usr/bin`).
* `/boot` (Boot): Chứa các tệp cần thiết để khởi động hệ thống, bao gồm **nhân Linux (kernel)** và các tệp cấu hình của **bootloader (như GRUB)**.
* `/dev` (Devices): Chứa các tệp thiết bị đại diện cho phần cứng và thiết bị ảo của hệ thống, như ổ đĩa (`/dev/sda`), bàn phím, chuột.
* `/etc` (Et Cetera / Editable Text Configuration): Chứa các tệp **cấu hình hệ thống và dịch vụ**, như cấu hình mạng, người dùng, dịch vụ khởi động.
* `/home` (Home): Chứa thư mục cá nhân của người dùng. Mỗi người dùng có một thư mục con trong `/home`, ví dụ: `/home/ngtukien`.
* `/lib` (Libraries): Chứa các thư viện chia sẻ cần thiết cho các chương trình trong `/bin` và `/sbin` để hoạt động. (Trên hệ thống của bạn, đây có thể là một liên kết tượng trưng đến `/usr/lib`).
* `/lib64` (Libraries 64-bit): Chứa các thư viện chia sẻ 64-bit, cần thiết cho các chương trình 64-bit. (Trên hệ thống mới, nó thường liên kết đến `/usr/lib`).
* `/lost+found` (Lost and Found): Thư mục được sử dụng bởi công cụ kiểm tra hệ thống tệp (`fsck`) để lưu trữ các tệp hoặc khối dữ liệu **bị hỏng hoặc mồ côi** được khôi phục sau sự cố hệ thống.
* `/media` (Media): Điểm gắn kết (mount point) mặc định cho các thiết bị lưu trữ di động như **USB, CD-ROM, thẻ SD** khi được cắm vào.
* `/mnt` (Mount): Một điểm gắn kết (mount point) **tạm thời** truyền thống, thường dùng cho quản trị viên để gắn kết thủ công các hệ thống tệp hoặc thiết bị lưu trữ.
* `/opt` (Optional): Dùng để **cài đặt các phần mềm tùy chọn** hoặc của bên thứ ba (không thuộc hệ điều hành cơ bản).
* `/proc` (Processes): Một **hệ thống tệp ảo** (không tồn tại trên đĩa), chứa thông tin thời gian thực về **tiến trình đang chạy** và **trạng thái nhân (kernel)**.
* `/root` (Root): Thư mục home **đặc biệt dành riêng cho người dùng quản trị (root)**.
* `/run` (Run): Một hệ thống tệp **tạm thời trong RAM**, chứa dữ liệu thời gian chạy (runtime) của các dịch vụ kể từ lần khởi động gần nhất (ví dụ: file PID, socket). Dữ liệu này **mất khi khởi động lại**.
* `/sbin` (System Binaries): Chứa các lệnh quản trị hệ thống thiết yếu, thường chỉ dành cho **người dùng root**, ví dụ: `fdisk`, `ifconfig`, `reboot`. (Trên hệ thống của bạn, đây có thể là liên kết tượng trưng đến `/usr/sbin`).
* `/snap` (Snap): Chứa các gói phần mềm **Snap**, một định dạng đóng gói ứng dụng do **Canonical (công ty mẹ của Ubuntu)** phát triển.
* `/srv` (Service): Chứa dữ liệu cho các **dịch vụ hệ thống** (ví dụ: máy chủ web, máy chủ FTP).
* `/sys` (System): Một **hệ thống tệp ảo** giống `/proc`, cung cấp giao diện để **xem và thay đổi thông số của kernel, thiết bị, và driver**.
* `/tmp` (Temporary): Chứa các **tệp tạm thời** được tạo bởi ứng dụng. Dữ liệu trong thư mục này thường bị **xóa sau mỗi lần khởi động lại**.
* `/usr` (Unix System Resources): Một trong những thư mục **lớn nhất**, chứa các chương trình, thư viện, tài liệu... **không thiết yếu cho việc khởi động**. Hầu hết các phần mềm do người dùng cài đặt sẽ nằm ở đây.
* `/var` (Variable): Chứa các tệp có **dữ liệu thay đổi liên tục khi hệ thống chạy**, quan trọng nhất là:
  * Tệp nhật ký (**/var/log**)
  * Bộ đệm (**/var/cache**)
  * Hàng đợi email, v.v.

