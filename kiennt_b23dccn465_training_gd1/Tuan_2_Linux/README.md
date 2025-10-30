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
  * Tệp nhật ký (`/var/log`)
  * Bộ đệm (`/var/cache`)
  * Hàng đợi email, v.v.
# Phần 2 : Làm quen với Terminal và Shell
## 1. Terminal & Shell là gì
* **Terminal** (Giao diện dòng lệnh) là một ứng dụng đồ họa cung cấp cho bạn một cửa sổ với giao diện dòng lệnh (CLI).
  * Nhiệm vụ: Đây là nơi bạn nhìn thấy và nhập các lệnh. Nó chịu trách nhiệm hiển thị văn bản, xử lý các phím bạn gõ, và hiển thị kết quả trả về.
  * Ví dụ: GNOME Terminal (mặc định của Ubuntu), Terminator, iTerm2 (trên macOS), Windows Terminal.
  * Terminal giống như ứng dụng nhắn tin (Viber, Zalo, Messenger) trên điện thoại của bạn. Nó cung cấp giao diện (ô nhập văn bản, màn hình chat) để bạn giao tiếp.
    ![terminal.png](Image/terminal.png)
* **Shell** (Bash, Zsh, Fish) là một chương trình chạy bên trong Terminal, chịu trách nhiệm **diễn giải và thực thi các lệnh** mà bạn nhập.
  * Nhiệm vụ: Khi bạn nhập một lệnh trong Terminal, Shell sẽ phân tích cú pháp, tìm chương trình tương ứng trên hệ thống, và chạy nó. Sau đó, nó sẽ hiển thị kết quả trả về trong Terminal.
  * Ví dụ: Bash (Bourne Again SHell) là shell mặc định trên hầu hết các hệ thống Linux, bao gồm cả Ubuntu. Ngoài ra còn có Zsh, Fish, v.v.
  * Shell giống như người phiên dịch trong cuộc trò chuyện. Khi bạn nói một câu, người phiên dịch sẽ hiểu ý bạn và truyền đạt nó đến người nghe.
## 2. Các lệnh cơ bản
* `pwd` : Hiển thị thư mục hiện tại mà bạn đang đứng.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ pwd
/home/ngtukien/Documents/TYP/typ-training-2025
```
* `ls` : Liệt kê các tệp (files) và thư mục (directories) bên trong thư mục hiện tại.
    * `ls`: Liệt kê cơ bản.
    * `ls -l`: Liệt kê dạng "long" (dài), hiển thị chi tiết (quyền, chủ sở hữu, kích thước, ngày giờ).
    * `ls -a`: Liệt kê "all" (tất cả), bao gồm cả các tệp/thư mục bị ẩn (bắt đầu bằng dấu `.`).
    * `ls -la`: Kết hợp cả hai, hiển thị tất cả tệp/thư mục một cách chi tiết.
```shell
ngtukien@NgTuKien:~/Documents/TYP$ ls -la
total 20
drwxrwxr-x 5 ngtukien ngtukien 4096 Oct 27 13:55 .
drwxr-xr-x 9 ngtukien ngtukien 4096 Oct 24 08:27 ..
drwxrwxr-x 2 ngtukien ngtukien 4096 Oct 27 13:56 .idea
drwxrwxr-x 5 ngtukien ngtukien 4096 Oct 27 16:15 lab_github
drwxrwxr-x 5 ngtukien ngtukien 4096 Oct 28 06:59 typ-training-2025
```
* `cd` (Change Directory) : Di chuyển đến một thư mục khác.
    * `cd /usr/bin`: Di chuyển đến thư mục `/usr/bin` (đường dẫn tuyệt đối).
    * `cd Documents`: Di chuyển vào thư mục `Documents` (nằm bên trong thư mục hiện tại).
    * `cd ..`: Di chuyển lùi lại 1 cấp (ra thư mục cha).
    * `cd ~` hoặc chỉ gõ `cd`: Quay về thư mục `home` của bạn (ví dụ: `/home/ngtukien`).
    * `cd -`: Quay lại thư mục bạn vừa rời khỏi (rất hữu ích).
* `clear` : Xóa sạch màn hình Terminal, đưa dấu nhắc lệnh lên trên cùng cho gọn gàng.
  * Bạn cũng có thể dùng `Ctrl + L` để có tác dụng tương tự.
* `history` : Hiển thị danh sách các lệnh bạn đã gõ trước đó.
    * `history`: Xem toàn bộ lịch sử.
    * `!50`: Thực thi lại lệnh số 50 trong danh sách.
    * `!!`: Thực thi lại lệnh ngay trước đó (rất hay dùng).
* `Tab` (Tự động hoàn thành)
    * Gõ một phần của tên lệnh hoặc tên tệp/thư mục, sau đó nhấn `Tab`.
    * **Nếu chỉ có 1 kết quả:** Shell sẽ tự động điền nốt phần còn lại cho bạn.
        * `cd Docu` + `Tab` ➔ `cd Documents/`
    * **Nếu có nhiều kết quả:** Nhấn `Tab` 2 lần, Shell sẽ liệt kê tất cả các lựa chọn bắt đầu bằng cụm từ đó.
```shell
ngtukien@NgTuKien:~$ ls Do
Documents/ Downloads/ 
ngtukien@NgTuKien:~$ ls Do
```
* `Ctrl + C` (Hủy bỏ) : Gửi tín hiệu "Interrupt" (Ngắt) để **dừng ngay lập tức** một chương trình hoặc lệnh đang chạy trong Terminal.
* `Ctrl + D` (Kết thúc đầu vào) : Gửi tín hiệu "End of File" (Kết thúc tệp), "End of Input" (Kết thúc nhập) hoặc thoát Terminal.
    * **Thoát Shell:** Nếu bạn đang ở dấu nhắc lệnh trống, nhấn `Ctrl + D` sẽ tương đương với lệnh `exit` (thoát khỏi Terminal).
    * **Kết thúc nhập liệu:** Khi đang chạy một chương trình cho phép bạn nhập nhiều dòng (như `cat`), nhấn `Ctrl + D` để báo "Tôi đã nhập xong".
## 3. Cấu trúc đường dẫn
* **Đường dẫn tuyệt đối :**
  * Là đường dẫn đầy đủ bắt đầu từ thư mục gốc (`/`).
  * Đường dẫn tuyệt đối luôn chỏ đến một vị trí cụ thể trên hệ thống tệp, bất kể bạn đang ở đâu trong cây thư mục.
  * Ví dụ : `/home/ngtukien/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md`
* **Đường dẫn tương đối :**
  * Là đường dẫn bắt đầu từ vị trí hiện tại của bạn trong hệ thống tệp.
  * Đường dẫn tương đối thay đổi tùy thuộc vào thư mục hiện tại mà bạn đang đứng.
  * Ví dụ :
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ pwd
/home/ngtukien/Documents/TYP/typ-training-2025
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ cat kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md 
# Phần 1 : Giới thiệu tổng quan về Linux
## 1. Linux là gì?
* Linux là nhân (kernel) của một hệ điều hành mã nguồn mở, được phát triển lần đầu bởi Linus Torvalds vào năm 1991 bằng ngôn ngữ lập trình C. 
* Nhân là thành phần cốt lõi, hoạt động như cầu nối trung gian giữa phần cứng và phần mềm.
* Tuy nhiên, khi nói về "Linux" trong ngữ cảnh phổ biến, chúng ta thường đề cập đến các hệ điều hành dựa trên nhân Linux, được gọi là các bản phân phối Linux (Linux distributions).
## 2. Lịch sử phát triển của Linux
* Người khởi xướng: Linus Torvalds, một sinh viên khoa học máy tính người Phần Lan.
* Thời điểm: Bắt đầu vào năm 1991.
...
```
* Ký hiệu đặc biệt trong đường dẫn:
  * `.` (dấu chấm đơn): Đại diện cho **thư mục hiện tại**.
  * `..` (hai dấu chấm): Đại diện cho **thư mục cha** (thư mục chứa thư mục hiện tại).
  * `~` (dấu ngã): Đại diện cho **thư mục home của người dùng hiện tại** (ví dụ: `/home/ngtukien`).
# Phần 3 : Làm việc với file và thư mục
## 1. Tạo, xem, xóa và di chuyển file
* `touch` : Tạo tập tin trống mới hoặc cập nhật dấu thời gian của tập tin đã tồn tại.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls -la
total 40
drwxrwxr-x 3 ngtukien ngtukien  4096 Oct 29 10:32 .
drwxrwxr-x 4 ngtukien ngtukien  4096 Oct 28 07:29 ..
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 28 11:29 Image
-rw-rw-r-- 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rw-rw-r-- 1 ngtukien ngtukien 24461 Oct 29 10:32 README.md
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ touch touch.md
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ touch README.md 
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls -la
total 40
drwxrwxr-x 3 ngtukien ngtukien  4096 Oct 29 10:33 .
drwxrwxr-x 4 ngtukien ngtukien  4096 Oct 28 07:29 ..
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 28 11:29 Image
-rw-rw-r-- 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rw-rw-r-- 1 ngtukien ngtukien 24461 Oct 29 10:33 README.md
-rw-rw-r-- 1 ngtukien ngtukien     0 Oct 29 10:33 touch.md
```
* `cat` : Đọc in ra toàn bộ nội dung của 1 hoặc nhiều tệp tin.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ echo "Cat" >> touch.md
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat touch.md 
Cat
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat touch.md README.md 
Cat
# Phần 1 : Giới thiệu tổng quan về Linux
## 1. Linux là gì?
* Linux là nhân (kernel) của một hệ điều hành mã nguồn mở, được phát triển lần đầu bởi Linus Torvalds vào năm 1991 bằng ngôn ngữ lập trình C. 
* Nhân là thành phần cốt lõi, hoạt động như cầu nối trung gian giữa phần cứng và phần mềm.
* Tuy nhiên, khi nói về "Linux" trong ngữ cảnh phổ biến, chúng ta thường đề cập đến các hệ điều hành dựa trên nhân Linux, được gọi là các bản phân phối Linux (Linux distributions).
## 2. Lịch sử phát triển của Linux
* Người khởi xướng: Linus Torvalds, một sinh viên khoa học máy tính người Phần Lan.
...
```
* `less` : Dùng để xem nội dung theo từng trang. Nó cho phép bạn cuộn lên/xuống để đọc nội dung dài.
    * Sử dụng phím `Space` để chuyển sang trang tiếp theo.
    * Sử dụng phím `b` để quay lại trang trước.
    * Nhấn `q` để thoát khỏi chế độ xem.
    * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat README.md | less
    ```
  ![less.png](Image/less.png)
* `head` & `tail`: Xem số lượng dòng nhất định của đầu (`head`) hoặc cuối (`tail`) 1 file, mặc định là 10
  * Cú pháp : `cat <file> | head<hoặc tail> -n <số_dòng>` hoặc `cat <file> | head<hoặc tail> -<số_dòng>` hoặc `head <hoặc tail> -n <số dòng> <file>`.
  * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat README.md | head
    # Phần 1 : Giới thiệu tổng quan về Linux
    ## 1. Linux là gì?
    * Linux là nhân (kernel) của một hệ điều hành mã nguồn mở, được phát triển lần đầu bởi Linus Torvalds vào năm 1991 bằng ngôn ngữ lập trình C. 
    * Nhân là thành phần cốt lõi, hoạt động như cầu nối trung gian giữa phần cứng và phần mềm.
    * Tuy nhiên, khi nói về "Linux" trong ngữ cảnh phổ biến, chúng ta thường đề cập đến các hệ điều hành dựa trên nhân Linux, được gọi là các bản phân phối Linux (Linux distributions).
    ## 2. Lịch sử phát triển của Linux
    * Người khởi xướng: Linus Torvalds, một sinh viên khoa học máy tính người Phần Lan.
    * Thời điểm: Bắt đầu vào năm 1991.
    * Động lực: Linus muốn tạo ra một nhân hệ điều hành miễn phí, giống UNIX, có thể chạy trên máy tính cá nhân (PC) của mình.
    * Phát triển ban đầu: Ban đầu, nó chỉ là một dự án "sở thích" cá nhân, không có ý định trở nên lớn mạnh hay chuyên nghiệp.
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat README.md | tail -5
    ![img.png](Image/less.png)
    * `head` : Xem số lượng dòng nhất định của đầu 1 file, mặc định là 10
    * `tail` : Xem số lượng dòng nhất định của cuối 1 file, mặc định là 10
    * Cú pháp : `cat <file> | head<hoặc tail> -n <số_dòng>` hoặc `cat <file> | head<hoặc tail> -<số_dòng>` hoặc `head <hoặc tail> -n <số dòng> <file>`.
    
    ```
* `cp` : Sao chép 1 hoặc nhiều tệp tin từ nơi này sang nơi khác. 
    * Cú pháp : `cp <nguồn> <đích>`.
    * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cp ../Tuan_1_Git_\&_Github/ssh_key.md ../Tuan_1_Git_\&_Github/Thuat_toan_SHA1.md .
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls ../Tuan_1_Git_\&_Github/
    Cach_SHA1_tao_ra_commitID.md  Image  README.md  ssh_key.md  Thuat_toan_SHA1.md
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  note.md  README.md  ssh_key.md  Thuat_toan_SHA1.md  touch.md
    ```
    * `cp -r <nguồn> <đích>` : Sao chép thư mục và toàn bộ nội dung bên trong nó (đệ quy).
    * `cp -a <nguồn> <đích>` : Sao chép toàn bộ (gồm cả quyền sở hữu, dấu thời gian, ...) (backup)
* `mv` : Di chuyển (hoặc đổi tên) 1 hoặc nhiều tệp tin từ nơi này sang nơi khác.
  * Cú pháp : `mv <nguồn> <đích>`.
  * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  note.md  README.md  ssh_key.md  Thuat_toan_SHA1.md  touch.md
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ mv ssh_key.md Thuat_toan_SHA1.md ../Tuan_1_Git_\&_Github/
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ mkdir Test
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cp Test/ ../Tuan_1_Git_\&_Github/
    cp: -r not specified; omitting directory 'Test/'
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ mv Test/ ../Tuan_1_Git_\&_Github/Tuan_2
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls ../Tuan_1_Git_\&_Github/
    Cach_SHA1_tao_ra_commitID.md  Image  README.md  ssh_key.md  Thuat_toan_SHA1.md  Tuan_2
    ```
* `rm` : Xóa 1 hoặc nhiều tệp tin.
    * Cú pháp : `rm <tệp1> <tệp2> ...`.
    * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls 
    Image  note.md  README.md  rename.md
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ rm rename.md 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls 
    Image  note.md  README.md
    ```
  * `rm -r <thư_mục>` : Xóa thư mục và toàn bộ nội dung bên trong nó (đệ quy).
  * `rm -i <tệp>` : Hỏi xác nhận trước khi xóa từng tệp (interactive).
  * `rm -f <tệp>` : Ép buộc xóa mà không hỏi lại (force).
  * `rm -rf <thư_mục>` : Kết hợp cả hai, xóa thư mục và toàn bộ nội dung bên trong nó mà không hỏi lại.
* `mkdir` : Tạo 1 hoặc nhiều thư mục rỗng
  * Cú pháp : `mkdir <tên_thư_mục>`
  * `mkdir -p <Thư_mục_cha>/<Thư_mục_con>` : Tạo thư mục con bên trong thư mục cha. Nếu thư mục cha chưa tồn tại, nó sẽ được tạo tự động.
* `rmdir` : Xóa thư mục rỗng
  * Cú pháp : `rmdir <tên_thư_mục>`
  * `rmdir -p <Thư_mục_cha>/<Thư_mục_con>` : Xóa thư mục con và nếu thư mục cha trở nên rỗng sau đó, nó cũng sẽ bị xóa.
  * Lưu ý : `rmdir` chỉ xóa được thư mục rỗng. Nếu thư mục có chứa tệp tin hoặc thư mục con, bạn cần dùng `rm -r` để xóa toàn bộ.
## 2. Sao chép và nén file.
* `tar` : Dùng để đóng gói nhiều file/dir lại thành 1 file duy nhất (archive).

    | Tùy chọn | Viết đầy đủ | Chức năng                                                |
    |--|-------------|----------------------------------------------------------|
    | `-c` | `--create`  | Tạo file archive mới                                     |
    | `-x` | `--extract` | Giải nén file archive                                    |
    | `-v` | `--verbose` | Hiển thị chi tiết quá trình (liệt kê file đang xử lý)    |
    | `-f` | `--file`    | Chỉ định tên file archive                                |
    | `-t` | `--list`    | Liệt kê nội dung trong file tar mà không giải nén        |
    | `-z` | `--gzip`    | Nén hoặc giải nén bằng gzip (`.tar.gz`, `.tgz`)          |
    | `-r` | `--append`  | Thêm file vào archive đã có (không dùng cho nén gzip/xz) |
    |  | `--help`    | Xem các option khác                                      |
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ tar -czvf image.tar.gz Image/
    Image/
    Image/less.png
    Image/terminal.png
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  image.tar.gz  note.md  README.md
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ tar -tzvf image.tar.gz 
    drwxrwxr-x ngtukien/ngtukien 0 2025-10-29 10:43 Image/
    -rw-rw-r-- ngtukien/ngtukien 57166 2025-10-29 10:41 Image/less.png
    -rw-rw-r-- ngtukien/ngtukien 35307 2025-10-28 11:29 Image/terminal.png
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ tar -xzvf image.tar.gz
    Image/
    Image/less.png
    Image/terminal.png
    ```
* `gzip` : Dùng để nép 1 tệp tin duy nhất. Sau khi nén, tệp tin sẽ bị xóa.
    * Ví dụ : 
    ```shell 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ gzip note.md 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  image.tar.gz  note.md.gz  README.md  
    ```
    * `gzip -k <tệp tin>` : Nén và giữ lại tệp tin
    * `gzip -d <tệp tin.gz>` hoặc `gunzip <tệp tin.gz>` : Giải nén tệp tin `.gz`
    ```shell 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ gzip -d note.md.gz 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ gzip -k note.md
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  image.tar.gz  note.md  note.md.gz  README.md  
    ```
* `zip` : Dùng để nén 1 hoặc nhiều tệp tin/thư mục thành 1 tệp tin `.zip`.
  * Khác với `tar`, `zip` sẽ nén từng tệp tin riêng lẻ bên trong tệp tin `.zip`.
  * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ zip readme.zip README.md note.md 
    adding: README.md (deflated 72%)
    adding: note.md (deflated 20%)
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  image.tar.gz  note.md  note.md.gz  README.md  readme.zip
    ```
  * Để nén 1 thư mục, nếu chỉ dùng `zip <tên_file_zip> <tên_thư_mục>`, `zip` sẽ chỉ nén thư mục rỗng, còn các tập tin và thư mục con sẽ không được nén.
    * Cần dùng thêm tùy chọn `-r` (recursive) để nén thư mục.
    * Ví dụ : 
      ```shell
      ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ zip image.zip Image/
      adding: Image/ (stored 0%)
      ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
      Image  image.zip  note.md  README.md
      ```
  * Phần trong ngoặc khi nén là cho biết số phần trăm dung lương được nén lại so với dung lượng gốc. Ví dụ :
    * `adding: Image/ (stored 0%)` tức thư mục `Image/` được giữ nguyên dung lượng vì nó chỉ là cái vỏ rỗng.
    * `adding: Image/less.png (deflated 6%)` tức file `Image/less.png` đã nén 6%, còn lại 94% dung lượng gốc.
* `unzip` : Giải nén tệp tin `.zip`.
* Ví dụ : 
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ unzip image.zip
    Archive:  image.zip
    replace Image/less.png? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
    inflating: Image/less.png          
    replace Image/terminal.png? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
    inflating: Image/terminal.png
    ```
  * `unzip -j <file_zip>` : giải nén file ngay tại thư mục hiện tại (không tạo thêm thư mục con).
  * `unzip -l <file_zip>` : liệt kê nội dung bên trong.
  * `unzip -t <file_zip>` : kiểm tra các file trong zip xem có bị hỏng hay không mà không giải nén.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ unzip -t image.zip 
    Archive:  image.zip
    testing: Image/                   OK
    testing: Image/less.png           OK
    testing: Image/terminal.png       OK
    No errors detected in compressed data of image.zip.
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ unzip -l image.zip
    Archive:  image.zip
    Length      Date    Time    Name
    ---------  ---------- -----   ----
        0  2025-10-29 14:37   Image/
    62397  2025-10-29 10:40   Image/less.png
    39340  2025-10-28 11:28   Image/terminal.png
    ---------                     -------
    101737                     3 files
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ unzip -j image.zip
    Archive:  image.zip
    inflating: less.png                
    inflating: terminal.png            
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls
    Image  image.zip  less.png  note.md  README.md  terminal.png
    ```
* `scp` (Secure copy) : Sao chép hoặc tải 1 tệp tin 1 cách an toàn từ máy này sang máy khác trên cùng 1 mạng.
  * Nó an toàn là vì sử dụng giao thức SSH để mã hóa dữ liệu trong quá trình truyền.
  * Cú pháp : `scp <tùy_chọn> <nguồn> <đích>`
  * `-r` : Sao chép toàn bộ thư mục.
  * `-P` : Dùng để chỉ định cổng (mặc định là cổng 22).
  * `-i` : Dùng để xác lập ssh-key thay vì dùng mật khẩu.
## 3. Giải thích khái niệm stream
"Stream" (luồng) là một khái niệm cơ bản trong Linux và các hệ thống giống Unix. Đây là các **kênh giao tiếp dữ liệu** (Input/Output) tiêu chuẩn mà mọi chương trình dòng lệnh đều tự động có khi nó khởi chạy.

Hãy tưởng tượng mỗi chương trình là một cỗ máy:

* **`stdin`** là cái phễu/khay **đầu vào** để bạn đưa nguyên liệu vào.
* **`stdout`** là băng chuyền cho **thành phẩm** (kết quả bình thường).
* **`stderr`** là một băng chuyền riêng cho **phế phẩm/lỗi** (thông báo lỗi).

Mặc định, cả ba luồng này đều được kết nối với terminal (cửa sổ dòng lệnh) của bạn.

-----
### a. stdin (Standard Input - Luồng vào chuẩn)

* **Mô tả:** Đây là luồng *nhận* dữ liệu mặc định của chương trình.
* **Nguồn mặc định:** **Bàn phím** của bạn.
* **Ví dụ:** Khi bạn chạy lệnh `cat` mà không có tham số, nó sẽ chờ dữ liệu từ `stdin`. Bất cứ thứ gì bạn gõ vào bàn phím sẽ được gửi qua `stdin` cho `cat`.
* **File Descriptor (Số mô tả tệp):** `0`

-----

### b. stdout (Standard Output - Luồng ra chuẩn)

* **Mô tả:** Đây là luồng *gửi ra* dữ liệu mặc định cho các kết quả **thành công** hoặc **bình thường** của chương trình.
* **Đích mặc định:** **Màn hình terminal**.
* **Ví dụ:** Khi bạn chạy `ls -l`, danh sách tệp tin nó in ra chính là `stdout`.
* **File Descriptor:** `1`

-----

### c. stderr (Standard Error - Luồng lỗi chuẩn)

* **Mô tả:** Đây là một luồng *gửi ra* dữ liệu thứ hai, được dành riêng cho các **thông báo lỗi**, **cảnh báo**, hoặc thông tin gỡ rối (diagnostic).
* **Đích mặc định:** **Màn hình terminal**.
* **Ví dụ:** Nếu bạn chạy `ls /folder-khong-ton-tai`, thông báo lỗi "No such file or directory" sẽ được gửi đến `stderr`.
* **File Descriptor:** `2`

-----

### 💡 Tại sao phải tách biệt stdout và stderr?

Đây chính là điểm "thiên tài" của thiết kế này. Mặc dù cả `stdout` và `stderr` đều in ra màn hình, việc chúng là hai luồng riêng biệt cho phép chúng ta **Điều Hướng (Redirection)** chúng một cách độc lập.

Điều này cực kỳ quan trọng trong scripting và tự động hóa.

**Tình huống 1: Chỉ lấy kết quả thành công, bỏ qua lỗi.**
Bạn muốn lưu danh sách tệp vào file, nhưng không muốn lưu các thông báo lỗi (ví dụ: "Permission denied").

```bash
# '>' là viết tắt của '1>' (điều hướng stdout - luồng 1)
# Kết quả 'ls' (stdout) sẽ vào file 'file_list.txt'
# Lỗi 'ls' (stderr) vẫn sẽ in ra màn hình
ls -l /etc /root > file_list.txt 
```

Trong ví dụ trên, `file_list.txt` sẽ chứa danh sách tệp của `/etc`, nhưng lỗi "Permission denied" khi truy cập `/root` sẽ vẫn hiển thị trên terminal của bạn, không bị lẫn vào file kết quả.

**Tình huống 2: Chỉ lấy lỗi, bỏ qua kết quả thành công.**
Bạn chạy một trình biên dịch và chỉ quan tâm đến lỗi (nếu có).

```bash
# '2>' (điều hướng stderr - luồng 2)
# Lỗi biên dịch (stderr) sẽ vào file 'compile_errors.log'
# Kết quả thành công (stdout - ví dụ: "Build successful") sẽ in ra màn hình
javac MyProgram.java 2> compile_errors.log
```

**Tình huống 3: Nối các lệnh với nhau (Piping).**
Dấu "ống" (`|`) là một cơ chế đặc biệt: nó lấy `stdout` (luồng 1) của lệnh bên trái và *nối* nó vào `stdin` (luồng 0) của lệnh bên phải.

```bash
# stdout của 'ls -l' trở thành stdin của 'grep'
ls -l | grep ".txt"
```

Quan trọng: Nếu `ls -l` tạo ra lỗi (ví dụ: "Permission denied"), lỗi đó (trên `stderr`) sẽ *không* bị `|` bắt. Nó vẫn sẽ in thẳng ra màn hình, trong khi `grep` chỉ nhận được danh sách tệp hợp lệ.

**Tình huống 4: Lưu tất cả mọi thứ vào một file log.**

```bash
# '2>&1' có nghĩa là: "Điều hướng luồng 2 (stderr) đến bất cứ nơi nào luồng 1 (stdout) đang trỏ tới"
sudo apt update > update_log.txt 2>&1
```

* `> update_log.txt`: Hướng `stdout` (luồng 1) vào `update_log.txt`.
* `2>&1`: Hướng `stderr` (luồng 2) vào cùng nơi với luồng 1 (tức là file `update_log.txt`).

Kết quả là cả output bình thường và output lỗi đều được ghi chung vào một file log.

## 4. Tìm kiếm file
* `find` (Tìm kiếm thời gian thực) : tìm kiếm trên cây thư mục bạn chỉ định và kiểm tra từng tệp/thư mục xem có khớp với các tiêu chí bạn đưa ra không.
  * **Cú pháp:** `find [nơi_bắt_đầu] [biểu_thức_tìm_kiếm]`
  * **Điểm mạnh:** Cực kỳ linh hoạt. Bạn có thể tìm theo:
      * Tên (`-name` hoặc `-iname` (không phân biệt hoa thường))
      * Loại (tệp, thư mục, link: `-type f`, `-type d`)
      * Kích thước (`-size`)
      * Ngày sửa đổi (`-mtime`)
      * Quyền (`-perm`)
  * **Điểm yếu:** Có thể chậm nếu tìm trong một thư mục lớn (như `/`) vì nó phải kiểm tra ổ cứng *ngay lập"*.
  * Ví dụ : 
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ find kiennt_b23dccn465_training_gd1/ -type f -name "*.md"
    kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md
    kiennt_b23dccn465_training_gd1/Tuan_2_Linux/note.md
    kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/README.md
    kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/ssh_key.md
    kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/Cach_SHA1_tao_ra_commitID.md
    kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/Thuat_toan_SHA1.md
    ```
* `locate` (Tìm kiếm qua Database) : tìm kiếm trong một cơ sở dữ liệu (database) tên là `mlocate.db`. Database này được tự động cập nhật (thường là mỗi ngày một lần) bởi một tiến trình gọi là `updatedb`.
  * **Cú pháp:** `locate [tên_tệp]`
  * **Điểm mạnh:** **Nhanh như chớp**. Bạn có thể tìm toàn bộ hệ thống trong chưa đầy một giây.
  * **Điểm yếu:** **Không phải thời gian thực**. Nếu bạn vừa tạo một tệp 5 phút trước, `locate` sẽ không tìm thấy nó cho đến khi database được cập nhật. (Bạn có thể chạy `sudo updatedb` để buộc nó cập nhật).
  * Ví dụ : 
  ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ locate /kiennt_b23dccn465_training_gd1 README.md
    /home/ngtukien/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_1_Git_&_Github/README.md
    /home/ngtukien/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md
    ```
* `grep` (Tìm kiếm BÊN TRONG tệp) : **không** dùng để tìm *tệp tin*. Nó dùng để tìm *văn bản bên trong tệp tin*.
  * **Cú pháp:** `grep [tùy_chọn] [mẫu_văn_bản] [tệp_cần_tìm_trong_đó]`
  * **Cách sử dụng chính:** Nó đọc một tệp (hoặc `stdin`) và in ra mọi dòng có chứa mẫu văn bản bạn tìm.
  *  Ví dụ : 
    ```shell
    ngtukien@NgTuKien:~$ find -name "*.png" | grep -i "LESS"
    ./Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/Image/less.png
    find: ‘./.local/share/Trash/expunged/412668199/Database’: Permission denied
    ./.local/lib/python3.10/site-packages/werkzeug/debug/shared/less.png
    ```
# Phần 4 : Quyền truy cập và người dùng
## 1. Người dùng và nhóm (User & Group)
### a. Kiểm tra danh tính 
* `whoami` (Who am i) : Hiển tên người dùng (username) hiện tại.
```shell
ngtukien@NgTuKien:~$ whoami
ngtukien
```
* `id` : Hiển thị thông tin chi tiết về người dùng hiện tại, bao gồm:
  * UID (User ID): Mã số định danh người dùng.
  * GID (Group ID): Mã số định danh nhóm chính của người dùng.
  * Các nhóm phụ mà người dùng thuộc về.
```shell
ngtukien@NgTuKien:~$ id 
uid=1000(ngtukien) gid=1000(ngtukien) groups=1000(ngtukien),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users),114(lpadmin),984(docker)
```
### b. Lệnh quản lý người dùng
* `adduser` : Thêm người dùng mới. Chỉ `root` mới được quyền dùng.
    * Cú pháp : `sudo adduser <tên_người_dùng_mới>`
    * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~$ sudo adduser testuser
    info: Adding user `testuser' ...
    info: Selecting UID/GID from range 1000 to 59999 ...
    info: Adding new group `testuser' (1001) ...
    info: Adding new user `testuser' (1001) with group `testuser (1001)' ...
    info: Creating home directory `/home/testuser' ...
    info: Copying files from `/etc/skel' ...
    New password:
    BAD PASSWORD: The password is shorter than 8 characters
    Retype new password:
    passwd: password updated successfully
    Changing the user information for testuser
    Enter the new value, or press ENTER for the default
    Full Name []: Nguyen Tu Kien
    Room Number []:         
    Work Phone []:
    Home Phone []:
    Other []:
    Is the information correct? [Y/n] Y
    info: Adding new user `testuser' to supplemental / extra groups `users' ...
    info: Adding user `testuser' to group `users' ...
    ```
* `deluser` : Xóa người dùng. Chỉ `root` mới được quyền dùng.
  * Cú pháp : `sudo deluser <tên_người_dùng>`
  * Ví dụ : 
    ```shell
    ngtukien@NgTuKien:~$ sudo deluser testuser
    info: Removing crontab ...
    info: Removing user `testuser' ...
    ```
### c. Lệnh thay đổi quyền hạn
* `su` (Substitute user) : Chuyển đổi người dùng hiện tại sang người dùng khác trong phiên làm việc hiện tại.
  * Cú pháp : `su <tên_người_dùng>`
  * Ví dụ :
    ```shell
    ngtukien@NgTuKien:~$ su newuser
    Password:
    newuser@NgTuKien:/home/ngtukien$
    ```
* `sudo` (Superuser do) : Thực thi lệnh với quyền của người dùng `root` hoặc người dùng khác.
    * Cú pháp : `sudo <lệnh_cần_thực_hiện>`
    * Ví dụ : 
    ```shell
    ngtukien@NgTuKien:~$ sudo deluser testuser
    [sudo] password for ngtukien:
    info: Removing crontab ...
    info: Removing user `testuser' ...
    ```
### d. Tệp tin cấu hình
* `/etc` : Thư mục chứa các thông tin nhạy cảm về người dùng và nhóm trên hệ thống.
* `/etc/passwd` : Chứa thông tin về tất cả người dùng trên hệ thống. Mỗi dòng đại diện cho một người dùng và bao gồm các trường như tên người dùng, UID, GID, thư mục home, shell mặc định, v.v.
```shell
ngtukien@NgTuKien:~$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:998:998:systemd Network Management:/:/usr/sbin/nologin
systemd-timesync:x:996:996:systemd Time Synchronization:/:/usr/sbin/nologin
dhcpcd:x:100:65534:DHCP Client Daemon,,,:/usr/lib/dhcpcd:/bin/false
messagebus:x:101:101::/nonexistent:/usr/sbin/nologin
syslog:x:102:102::/nonexistent:/usr/sbin/nologin
systemd-resolve:x:991:991:systemd Resolver:/:/usr/sbin/nologin
uuidd:x:103:103::/run/uuidd:/usr/sbin/nologin
usbmux:x:104:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
tss:x:105:105:TPM software stack,,,:/var/lib/tpm:/bin/false
systemd-oom:x:990:990:systemd Userspace OOM Killer:/:/usr/sbin/nologin
kernoops:x:106:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
whoopsie:x:107:109::/nonexistent:/bin/false
dnsmasq:x:999:65534:dnsmasq:/var/lib/misc:/usr/sbin/nologin
avahi:x:108:111:Avahi mDNS daemon,,,:/run/avahi-daemon:/usr/sbin/nologin
tcpdump:x:109:112::/nonexistent:/usr/sbin/nologin
sssd:x:110:113:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
speech-dispatcher:x:111:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
cups-pk-helper:x:112:114:user for cups-pk-helper service,,,:/nonexistent:/usr/sbin/nologin
fwupd-refresh:x:989:989:Firmware update daemon:/var/lib/fwupd:/usr/sbin/nologin
saned:x:113:116::/var/lib/saned:/usr/sbin/nologin
geoclue:x:114:117::/var/lib/geoclue:/usr/sbin/nologin
cups-browsed:x:115:114::/nonexistent:/usr/sbin/nologin
hplip:x:116:7:HPLIP system user,,,:/run/hplip:/bin/false
gnome-remote-desktop:x:988:988:GNOME Remote Desktop:/var/lib/gnome-remote-desktop:/usr/sbin/nologin
polkitd:x:987:987:User for polkitd:/:/usr/sbin/nologin
rtkit:x:117:119:RealtimeKit,,,:/proc:/usr/sbin/nologin
colord:x:118:120:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
gnome-initial-setup:x:119:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:120:121:Gnome Display Manager:/var/lib/gdm3:/bin/false
nm-openvpn:x:121:122:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
strongswan:x:122:65534::/var/lib/strongswan:/usr/sbin/nologin
ngtukien:x:1000:1000:Nguyen Tu Kien:/home/ngtukien:/bin/bash
mysql:x:123:124:MySQL Server,,,:/nonexistent:/bin/false
newuser:x:1001:1001:,,,:/home/newuser:/bin/bash
```
* Mỗi dòng là một người dùng, các trường được phân tách bằng dấu hai chấm `:`. 
* Ví dụ : `ngtukien:x:1000:1000:Nguyen Tu Kien:/home/ngtukien:/bin/bash`
  * `ngtukien` : Tên đăng nhập
  * `x` : Mật khẩu. Chữ `x` có nghĩa là mật khẩu thực tế được mã hóa và lưu trữ trong tệp `/etc/shadow` (để bảo mật hơn).
  * `1000` : User ID (UID).
  * `1000` : Group ID (GID) (Nhóm chính).
  * `Nguyen Tu Kien` : Tên đầy đủ và thông tin (Gọi là GEGOS).
  * `/home/ngtukien` : Thư mục home.
  * `/bin/dash` : Shell mặc định (chương trình dòng lệnh sẽ chạy khi đăng nhập).
## 2. Phân quyền file
### a. 🔍 Cách Đọc Quyền (`ls -l` và `rwx`)
* Cú pháp : `ls -l`
* Ví dụ : 
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l
total 4
drwxrwxr-x 4 ngtukien ngtukien 4096 Oct 28 07:29 kiennt_b23dccn465_training_gd1
```
Chuỗi này được chia thành 4 phần:

| Phần | Ký Tự (Ví dụ) | Ý Nghĩa |
| :--- |:--------------| :--- |
| **1** | `d`           | **Loại (Type):** `d` là thư mục (directory), `-` là tệp tin (file). |
| **2** | `rwx`         | **Chủ sở hữu (User/Owner):** Quyền của người dùng sở hữu tệp này. |
| **3** | `rwx`         | **Nhóm (Group):** Quyền của các thành viên trong nhóm sở hữu tệp này. |
| **4** | `r-x`         | **Những người khác (Others):** Quyền của tất cả những người dùng còn lại. |
* Ý nghĩa của `r`, `w`, `x` : **khác nhau** tùy thuộc nó là Tệp tin hay Thư mục

| Quyền | Đối với Tệp Tin (File) | Đối với Thư Mục (Directory) |
| :--- | :--- | :--- |
| **`r` (Read)** | Được phép **đọc** nội dung tệp (ví dụ: `cat file.txt`). | Được phép **liệt kê** nội dung bên trong thư mục (ví dụ: `ls folder`). |
| **`w` (Write)** | Được phép **thay đổi** hoặc xóa nội dung tệp. | Được phép **tạo tệp mới** hoặc **xóa tệp** bên trong thư mục. |
| **`x` (Execute)** | Được phép **chạy** tệp đó như một chương trình (ví dụ: `./script.sh`). | Được phép **đi vào** (truy cập) thư mục (ví dụ: `cd folder`). |
> **Lưu ý quan trọng:** Để `cd` vào một thư mục, bạn cần quyền `x`. Để `ls` xem thư mục đó, bạn cần quyền `r`. Đây là lý do tại sao các thư mục thường có quyền `r-x` (cho phép vào xem).

### b. ⚙️ Cách Thay Đổi Quyền (`chmod`) 
Lệnh `chmod` (**ch**ange **mod**e) dùng để thay đổi quyền `rwx` cho tệp tin/thư mục. Có hai cách dùng chính:
#### Cách 1: Bằng Ký Hiệu (Symbolic) - Dễ nhớ
Bạn sử dụng các chữ cái để chỉ định ai, làm gì, và quyền gì.
* **Ai:** `u` (user), `g` (group), `o` (others), `a` (all - tất cả).
* **Làm gì:** `+` (thêm quyền), `-` (bớt quyền), `=` (gán quyền chính xác).
* **Quyền gì:** `r`, `w`, `x`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l kiennt_b23dccn465_training_gd1/Tuan_2_Linux/
total 68
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 29 15:27 Image
-rw-rw-r-- 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rw-rw-r-- 1 ngtukien ngtukien 59418 Oct 30 09:37 README.md
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ chmod u=rwx,go=rwx kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md 
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l kiennt_b23dccn465_training_gd1/Tuan_2_Linux/
total 68
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 29 15:27 Image
-rw-rw-r-- 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rwxrwxrwx 1 ngtukien ngtukien 59406 Oct 30 09:41 README.md
```
#### Cách 2: Bằng Số (Octal) - Phổ biến nhất
Bạn dùng 3 con số để đại diện cho quyền của User, Group, và Others. Mỗi con số là tổng của các quyền:
* `r` (read) = **4** (100)
* `w` (write) = **2** (010)
* `x` (execute) = **1** (001)

**Các tổ hợp phổ biến:**
* `7` = 4 + 2 + 1 = `rwx` (Toàn quyền)
* `6` = 4 + 2 + 0 = `rw-` (Đọc và ghi)
* `5` = 4 + 0 + 1 = `r-x` (Đọc và thực thi/truy cập)
* `4` = 4 + 0 + 0 = `r--` (Chỉ đọc)
* `0` = 0 + 0 + 0 = `---` (Không có quyền)
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l kiennt_b23dccn465_training_gd1/Tuan_2_Linux/
total 68
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 29 15:27 Image
-rw-rw-r-- 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rwxrwxrwx 1 ngtukien ngtukien 59406 Oct 30 09:41 README.md
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ chmod 777 kiennt_b23dccn465_training_gd1/Tuan_2_Linux/note.md 
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l kiennt_b23dccn465_training_gd1/Tuan_2_Linux/
total 68
drwxrwxr-x 2 ngtukien ngtukien  4096 Oct 29 15:27 Image
-rwxrwxrwx 1 ngtukien ngtukien    25 Oct 29 10:29 note.md
-rwxrwxrwx 1 ngtukien ngtukien 59787 Oct 30 09:43 README.md
```
> **Mẹo:** Để thay đổi quyền cho tất cả các tệp/thư mục con bên trong, hãy dùng cờ `-R` (Recursive):
> `chmod -R 755 my_project_folder/`
### c. 👤 Cách Thay Đổi Chủ Sở Hữu (`chown`, `chgrp`)
Đôi khi, bạn cần thay đổi ai là người sở hữu tệp tin. Các lệnh này thường yêu cầu `sudo`.
* **`chown`** (**Ch**ange **Own**er)
  Lệnh này dùng để thay đổi **người dùng** sở hữu tệp tin.
    ```bash
    sudo chown ngtukien kiennt_b23dccn465_training_gd1/
    ```
  > **Mẹo hay nhất:** `chown` cũng có thể thay đổi **cả người dùng và nhóm** cùng một lúc bằng dấu hai chấm (`:`). Đây là cách dùng được khuyên.

  ```bash
  # Chuyển quyền sở hữu 'file.txt' cho người dùng 'newuser' VÀ nhóm 'newgroup'
  sudo chown ngtukien:Linux kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md
  ```
* **`chgrp`** (**Ch**ange **Gr**ou**p**)
  Lệnh này chỉ dùng để thay đổi **nhóm** sở hữu tệp tin. (Lệnh này ít được dùng hơn vì `chown` ở trên đã làm được việc này).
  ```bash
  sudo chgrp Linux ngtukien:Linux kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md
  ```
## 3. Quyền root và an toàn
### a. 🛑 Tại Sao Không Nên Chạy Mọi Thứ Bằng Root
Chạy mọi thứ với tư cách `root` (siêu quản trị) cũng giống như bạn lái xe trong thành phố mà không bao giờ dùng dây an toàn, đèn tín hiệu hay phanh. `root` là tài khoản "thần thánh", nó **bỏ qua mọi rào cản bảo vệ** của hệ thống.
Lý do chính là:

**1. Sai lầm của con người (Human Error)  destructive hơn**

Quyền lực của `root` không có "undo".

* **Tình huống (Người dùng bình thường):** Bạn gõ nhầm lệnh `rm -rf *` trong thư mục `~/Documents`. Bạn sẽ chỉ xóa các tệp tài liệu của mình. Rất tệ, nhưng máy tính vẫn chạy.
* **Tình huống (Người dùng `root`):** Bạn gõ nhầm lệnh `rm -rf *` trong thư mục `/etc` (hoặc tệ hơn là `/`). Bạn sẽ **xóa toàn bộ hệ điều hành**. Máy tính sẽ "chết" ngay lập tức và bạn phải cài đặt lại từ đầu.

**2. Lỗ hổng bảo mật (Security Risks)**
Đây là rủi ro lớn nhất.

* **Tình huống:** Bạn chạy một chương trình (ví dụ: trình duyệt web, một script tải từ mạng,...) với tư cách `root`. Nếu chương trình đó có một lỗ hổng bảo mật, kẻ tấn công (hacker) có thể lợi dụng nó.
* **Kết quả:** Vì bạn chạy chương trình bằng `root`, kẻ tấn công ngay lập tức **chiếm được toàn bộ quyền `root`** của máy bạn. Chúng có thể cài đặt virus, đánh cắp mật khẩu, xóa dữ liệu, hoặc biến máy của bạn thành máy đào tiền ảo.
* **Nếu bạn chạy bằng người dùng thường (`ngtukien`):** Kẻ tấn công sẽ chỉ chiếm được quyền của `ngtukien`. Chúng chỉ có thể phá các tệp trong `/home/ngtukien` và không thể làm hỏng hệ điều hành hoặc xem trộm tệp của người dùng khác.

> **Nguyên tắc vàng:** Luôn luôn sử dụng **Nguyên Tắc Đặc Quyền Tối Thiểu (Principle of Least Privilege)**. Nghĩa là: Chỉ sử dụng quyền hạn tối thiểu cần thiết để hoàn thành công việc. (99% công việc hàng ngày như lập trình, duyệt web, văn bản... đều không cần `root`).

---

### b. 🔑 Phân Biệt `sudo` và `su`
Cả hai đều dùng để nâng quyền, nhưng triết lý hoạt động hoàn toàn khác nhau.

**`su` (Substitute User - Thay thế Người dùng)**
* **Là gì:** Đây là lệnh để **chuyển đổi hoàn toàn** (đăng nhập) sang một tài khoản khác. Nếu không chỉ định, nó sẽ mặc định chuyển sang `root`.
* **Cách dùng:** Gõ `su -` (hoặc chỉ `su`).
* **Hỏi mật khẩu:** Nó hỏi mật khẩu của **`root`**.
* **Kết quả:** Shell của bạn biến thành shell của `root`. Dấu nhắc `$ ` chuyển thành `# `. Bạn *trở thành* `root` và mọi lệnh bạn gõ sau đó đều là lệnh của `root`, cho đến khi bạn gõ `exit`.
* **Nhược điểm:** Bạn phải biết và chia sẻ mật khẩu `root` (rất mất an toàn). Hệ thống chỉ ghi lại "ngtukien đã trở thành root" chứ không ghi lại chi tiết các lệnh bạn đã chạy sau đó.

**`sudo` (Superuser Do - Làm với quyền Siêu quản trị)**
* **Là gì:** Đây là lệnh để **chỉ chạy một lệnh duy nhất** *với tư cách* (as) `root`.
* **Cách dùng:** Gõ `sudo [lệnh_bạn_muốn_chạy]` (ví dụ: `sudo apt update`).
* **Hỏi mật khẩu:** Nó hỏi mật khẩu của **bạn** (`ngtukien`).
* **Kết quả:** Chỉ lệnh `apt update` đó được chạy với quyền `root`. Ngay khi lệnh đó kết thúc, bạn ngay lập tức quay lại là người dùng `ngtukien` bình thường.
* **Ưu điểm:** Cực kỳ an toàn. Bạn không cần biết mật khẩu `root`. Hệ thống ghi log (nhật ký) lại chính xác *từng lệnh* mà bạn đã chạy với `sudo`. Đây là cách làm được khuyên dùng.
# Phần 5 : Quản lý tiến trình và hệ thống

