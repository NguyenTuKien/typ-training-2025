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
* **Người dùng (User):** Là một "cá nhân" (như bạn, `ngtukien`). Mỗi người dùng sở hữu file và thư mục của riêng mình.
  * **Người dùng hệ thống (System Users):** Được tạo tự động cho các dịch vụ (ví dụ: `www-data` cho web server) để chạy các tiến trình một cách an toàn, bị giới hạn.
  * **Người dùng thông thường (Regular Users):** Là bạn (`ngtukien`). Bạn có một thư mục `/home/ngtukien` và có toàn quyền trong đó, nhưng bị hạn chế ở các khu vực khác của hệ thống.
  * **Superuser (root):** Là "quản trị viên tối cao". Người dùng `root` có quyền làm *mọi thứ* trên hệ thống. Đây là lý do bạn thường phải dùng lệnh `sudo` (SuperUser DO) để thực hiện các tác vụ quản trị.
* **Nhóm (Group):** Là một "câu lạc bộ" mà các người dùng có thể tham gia. Thay vì cấp quyền cho từng cá nhân, bạn có thể cấp quyền cho cả "câu lạc bộ".
* **Ví dụ:** Thay vì cấp quyền sửa file cho 3 người dùng (user\_A, user\_B, user\_C), bạn chỉ cần:
    1.  Tạo một nhóm tên là `developers`.
    2.  Thêm 3 người dùng đó vào nhóm `developers`.
    3.  Cấp quyền "sửa" cho nhóm `developers` trên file đó.
* Mỗi người dùng khi được tạo ra sẽ tự động thuộc về một nhóm chính (primary group) có tên trùng với tên người dùng đó (ví dụ: user `ngtukien` thuộc nhóm `ngtukien`).*
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
    ...
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
### a. Cách Đọc Quyền (`ls -l` và `rwx`)
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

### b. Cách Thay Đổi Quyền (`chmod`) 
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
### c. Cách Thay Đổi Chủ Sở Hữu (`chown`, `chgrp`)
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
### a. Tại Sao Không Nên Chạy Mọi Thứ Bằng Root
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
### b. Phân Biệt `sudo` và `su`
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
## 1. Quản lý tiến trình
### a. Xem và Giám sát Tiến trình
* **`ps` (Process Status):**
    * **Mục đích:** "Chụp ảnh" (snapshot) các tiến trình đang chạy tại *thời điểm* bạn gõ lệnh. Nó không cập nhật theo thời gian thực.
    * **Cách dùng phổ biến:** `ps aux`
        * `a`: Hiển thị tiến trình của tất cả người dùng.
        * `u`: Hiển thị định dạng chi tiết (user-oriented), cho biết ai là người chạy.
        * `x`: Hiển thị cả các tiến trình không được gắn với terminal (ví dụ: các dịch vụ hệ thống).
    * **Cột quan trọng:** `PID` (Process ID - Mã định danh tiến trình), `USER`, `%CPU`, `%MEM`, `COMMAND`.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | head
    USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root           1  0.1  0.0  23392 14376 ?        Ss   13:04   0:01 /sbin/init splash
    root           2  0.0  0.0      0     0 ?        S    13:04   0:00 [kthreadd]
    root           3  0.0  0.0      0     0 ?        S    13:04   0:00 [pool_workqueue_release]
    root           4  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/R-rcu_gp]
    root           5  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/R-sync_wq]
    root           6  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/R-kvfree_rcu_reclaim]
    root           7  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/R-slub_flushwq]
    root           8  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/R-netns]
    root          10  0.0  0.0      0     0 ?        I<   13:04   0:00 [kworker/0:0H-events_highpri]  
    ```
* **`top` (Table of Processes):**
    * **Mục đích:** Giám sát tiến trình theo *thời gian thực*. Nó giống như Task Manager trên Windows.
    * **Cách dùng:** Chỉ cần gõ `top`. Danh sách sẽ tự động cập nhật (thường là 3 giây một lần).
    * **Tương tác:** Mặc định sắp xếp theo `%CPU`. Bạn có thể tương tác khi nó đang chạy:
        * Nhấn `M` (chữ M viết hoa) để sắp xếp theo bộ nhớ (`%MEM`).
        * Nhấn `P` (chữ P viết hoa) để sắp xếp lại theo CPU.
        * Nhấn `k` để "kill" một tiến trình (nó sẽ hỏi PID).
        * Nhấn `q` để thoát.
    ```shell 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ top
    top - 13:32:48 up 28 min,  1 user,  load average: 0.54, 0.85, 0.70
    Tasks: 353 total,   1 running, 352 sleeping,   0 stopped,   0 zombie
    %Cpu(s):  7.2 us,  1.5 sy,  0.0 ni, 91.2 id,  0.1 wa,  0.0 hi,  0.1 si,  0.0 st 
    MiB Mem :  15769.7 total,   5728.7 free,   6097.8 used,   4718.5 buff/cache     
    MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.   9671.9 avail Mem 
    
    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                                                                                              
    3558 ngtukien  20   0   14.7g   2.8g 987848 S  75.7  18.1   9:09.51 java                                                                                                                 
    2754 ngtukien  20   0 4974864 309824 131072 S  12.3   1.9   1:05.53 gnome-shell                                                                                                          
    3604 ngtukien  20   0  572724  97416  66960 S   8.3   0.6   0:11.90 Xwayland                                                                                                             
    3679 ngtukien  20   0 1019868  88784  70736 S   2.7   0.5   0:00.72 mutter-x11-fram                                                                                                      
    4364 ngtukien  20   0 1392.5g 543284 149288 S   1.3   3.4   2:10.35 brave                                                                                                                
    4282 ngtukien  20   0   33.1g 226316 135524 S   1.0   1.4   0:55.16 brave                                                                                                                
    4241 ngtukien  20   0   33.0g 499372 291992 S   0.7   3.1   1:17.51 brave                                                                                                                
    4862 root       0 -20       0      0      0 D   0.7   0.0   0:02.66 kworker/u49:1+i915_flip                                                                                              
     18 root      20   0       0      0      0 I   0.3   0.0   0:01.23 rcu_preempt                                                                                                          
    2947 ngtukien  20   0  388836  11984   6932 S   0.3   0.1   0:02.39 ibus-daemon                                                                                                          
    3313 ngtukien  20   0  843972  41604  31352 S   0.3   0.3   0:01.25 xdg-desktop-por                                                                                                      
    4494 ngtukien  20   0 1399.1g 552856 162160 S   0.3   3.4   3:21.14 brave   
    ```
* **`htop`:**
    * **Mục đích:** Là phiên bản nâng cấp, thân thiện và nhiều màu sắc hơn của `top`.
    * **Cách dùng:** Tương tự `top`, nhưng thường không được cài đặt sẵn. Bạn cần cài nó (ví dụ: `sudo apt install htop` trên Ubuntu hoặc `brew install htop` trên macOS).
    * **Ưu điểm:** Cho phép cuộn (scroll) danh sách, dùng các phím F (F9 để kill), và đôi khi dùng được chuột. Trực quan hơn `top`.
  ![htop.png](Image/htop.png)
### b. Dừng và Gửi Tín hiệu đến Tiến trình
* **`kill`:**
    * **Mục đích:** Gửi một *tín hiệu* (signal) đến một tiến trình, yêu cầu nó làm gì đó. Cần **PID** của tiến trình.
    * **Cách dùng:**
        * `kill <PID>`: Gửi tín hiệu mặc định là `SIGTERM` (15). Đây là yêu cầu "dừng một cách lịch sự", cho phép tiến trình dọn dẹp trước khi thoát.
        * `kill -9 <PID>` hoặc `kill -SIGKILL <PID>`: Gửi tín hiệu `SIGKILL` (9). Đây là lệnh "giết" bắt buộc, buộc tiến trình phải dừng ngay lập tức. Chỉ dùng khi `kill` thường không hiệu quả.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
    root        1538  0.0  0.5 2660232 86296 ?       Ssl  13:04   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
    root        6667  0.0  0.0 1745184 4556 ?        Sl   13:38   0:00 /usr/bin/docker-proxy -proto tcp -host-ip 0.0.0.0 -host-port 1433 -container-ip 172.17.0.2 -container-port 1433 -use-listen-fd
    root        6675  0.0  0.0 1745440 4520 ?        Sl   13:38   0:00 /usr/bin/docker-proxy -proto tcp -host-ip :: -host-port 1433 -container-ip 172.17.0.2 -container-port 1433 -use-listen-fd
    ngtukien    6792  0.0  0.0   9144  2236 pts/0    S+   13:38   0:00 grep --color=auto docker
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo kill 6667
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
    root        1538  0.0  0.5 2733964 83312 ?       Ssl  13:04   0:01 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
    root        6675  0.0  0.0 1745440 4520 ?        Sl   13:38   0:00 /usr/bin/docker-proxy -proto tcp -host-ip :: -host-port 1433 -container-ip 172.17.0.2 -container-port 1433 -use-listen-fd
    ngtukien    7325  0.0  0.0   9144  2236 pts/0    S+   13:43   0:00 grep --color=auto docker
    ```
* **`killall`:**
    * **Mục đích:** Tương tự `kill`, nhưng gửi tín hiệu dựa trên **tên** của tiến trình, thay vì PID.
    * **Cách dùng:** `killall firefox`
    * **Lưu ý:** Lệnh này sẽ "giết" *tất cả* các tiến trình có tên khớp. Hãy cẩn thận khi sử dụng.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep brave | head 
ngtukien    7514  0.0  0.0   9940  3680 ?        S    13:46   0:00 /bin/bash /usr/bin/brave-browser-stable
ngtukien    7523 36.7  3.1 34553332 507108 ?     SLl  13:46   0:12 /opt/brave.com/brave/brave
ngtukien    7525  0.0  0.0 33577576 3948 ?       Sl   13:46   0:00 /opt/brave.com/brave/chrome_crashpad_handler --monitor-self --monitor-self-annotation=ptype=crashpad-handler --database=/home/ngtukien/.config/BraveSoftware/Brave-Browser/Crash Reports --metrics-dir=/home/ngtukien/.config/BraveSoftware/Brave-Browser --url=https://cr.brave.com --annotation=lsb-release=Ubuntu 24.04.3 LTS --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=141.1.83.120 --initial-client-fd=5 --shared-client-connection
ngtukien    7527  0.0  0.0 33568340 3376 ?       Sl   13:46   0:00 /opt/brave.com/brave/chrome_crashpad_handler --no-periodic-tasks --monitor-self-annotation=ptype=crashpad-handler --database=/home/ngtukien/.config/BraveSoftware/Brave-Browser/Crash Reports --url=https://cr.brave.com --annotation=lsb-release=Ubuntu 24.04.3 LTS --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=141.1.83.120 --initial-client-fd=4 --shared-client-connection
ngtukien    7533  0.1  0.4 34255556 74408 ?      S    13:46   0:00 /opt/brave.com/brave/brave --type=zygote --no-zygote-sandbox --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable
ngtukien    7534  0.0  0.4 34255544 74040 ?      S    13:46   0:00 /opt/brave.com/brave/brave --type=zygote --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable
ngtukien    7536  0.0  0.1 34255568 18664 ?      S    13:46   0:00 /opt/brave.com/brave/brave --type=zygote --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable
ngtukien    7568  2.5  1.1 34676952 184212 ?     Sl   13:46   0:00 /opt/brave.com/brave/brave --type=gpu-process --ozone-platform=wayland --render-node-override=/dev/dri/renderD129 --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable --gpu-preferences=UAAAAAAAAAAgAAAEAAAAAAAAAAAAAGAAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAYAAAAAAAAABgAAAAAAAAAAAAAAAAAAAAIAAAAAAAAAAgAAAAAAAAA --shared-files --metrics-shmem-handle=4,i,15571609829161852267,15395189341315675210,262144 --field-trial-handle=3,i,10496865386665040724,13212810554470718975,262144 --disable-features=EyeDropper --variations-seed-version=main@7d31d712bdf980905077eebd66b86d4a2dab3e79
ngtukien    7570  8.3  0.8 34028072 144104 ?     Sl   13:46   0:02 /opt/brave.com/brave/brave --type=utility --utility-sub-type=network.mojom.NetworkService --lang=en-US --service-sandbox-type=none --render-node-override=/dev/dri/renderD129 --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable --shared-files=v8_context_snapshot_data:100 --metrics-shmem-handle=4,i,131701062066062025,16317993879912146736,524288 --field-trial-handle=3,i,10496865386665040724,13212810554470718975,262144 --disable-features=EyeDropper --variations-seed-version=main@7d31d712bdf980905077eebd66b86d4a2dab3e79
ngtukien    7583  0.1  0.3 34306688 58820 ?      Sl   13:46   0:00 /opt/brave.com/brave/brave --type=utility --utility-sub-type=storage.mojom.StorageService --lang=en-US --service-sandbox-type=utility --render-node-override=/dev/dri/renderD129 --crashpad-handler-pid=7525 --enable-crash-reporter=53fec4a3-9ba7-4e68-83a8-04ef242295f5, --change-stack-guard-on-fork=enable --shared-files=v8_context_snapshot_data:100 --metrics-shmem-handle=4,i,9801742726285065673,12031593033250132176,524288 --field-trial-handle=3,i,10496865386665040724,13212810554470718975,262144 --disable-features=EyeDropper --variations-seed-version=main@7d31d712bdf980905077eebd66b86d4a2dab3e79
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ killall brave
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep brave | head 
ngtukien    8075  0.0  0.0   9144  2212 pts/0    S+   13:46   0:00 grep --color=auto brave
```
### c. 🏃‍♂️ Tiến trình Nền (Background) và Nổi (Foreground)
* **Foreground Process (Tiến trình nổi):**
    * Đây là chế độ mặc định. Khi bạn chạy một lệnh (ví dụ `sleep 300`), terminal của bạn bị "khóa" (block) và bạn không thể gõ lệnh mới cho đến khi lệnh đó chạy xong.
    * Bạn có thể hủy tiến trình foreground bằng `Ctrl + C` (gửi tín hiệu `SIGINT`).
* **Background Process (Tiến trình nền):**
    * **`&` (Dấu và):** Đặt `&` ở cuối lệnh để chạy nó ở chế độ nền.
        * **Ví dụ:** `sleep 300 &`
        * Terminal sẽ trả về ngay lập tức, hiển thị một `[job_id]` và `PID`, cho phép bạn tiếp tục gõ lệnh khác trong khi `sleep` vẫn đang chạy.
* **Quản lý Jobs (Các tiến trình trong terminal):**
    * **`Ctrl + Z`:** Nếu một lệnh đang chạy ở *foreground*, nhấn `Ctrl + Z` sẽ *tạm dừng* (Suspend) nó.
    * **`jobs`:** Gõ lệnh này để xem danh sách các "job" (tiến trình) đang bị tạm dừng hoặc đang chạy nền trong terminal hiện tại của bạn.
    * **`bg` (Background):** Sau khi tạm dừng một tiến trình bằng `Ctrl + Z`, gõ `bg` (có thể kèm theo `%job_id`, ví dụ `bg %1`) để nó *tiếp tục chạy* ở chế độ nền.
    * **`fg` (Foreground):** Gõ `fg %job_id` (ví dụ `fg %1`) để "kéo" một tiến trình đang chạy nền hoặc đang tạm dừng quay trở lại *foreground*.
    * `+` : Tiến trình đang tạm dừng hoặc chạy nền gần đây nhất.
    * `-` : Tiến trình tạm dừng hoặc chạy nền trước đó.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sleep 300
    ^C
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sleep 300 &
    [1] 8843
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bg
    bash: bg: job 1 already in background
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep 8843
    ngtukien    8843  0.0  0.0   8288  1932 pts/0    S    13:50   0:00 sleep 300
    ngtukien    8944  0.0  0.0   9144  2220 pts/0    S+   13:51   0:00 grep --color=auto 8843
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ fg
    sleep 300
    
    ^Z
    [1]+  Stopped                 sleep 300
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bg
    [1]+ sleep 300 &
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ fg
    sleep 300
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sleep 1000
    ^Z
    [1]+  Stopped                 sleep 1000
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bg
    [1]+ sleep 1000 &
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sleep 1000
    ^Z
    [2]+  Stopped                 sleep 1000
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bg
    [2]+ sleep 1000 &
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ fg %1
    sleep 1000
    ^Z
    [1]+  Stopped                 sleep 1000
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ kill %1
    [1]+  Terminated              sleep 1000
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ fg
    sleep 1000
    ^Z  
    [2]+  Stopped                 sleep 1000
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bg
    [2]+ sleep 1000 &
    ```
## 2. Kiểm tra tài nguyên hệ thống
### a. Quản lý Ổ đĩa (Disk)
* **`df` (Disk Free):**
    * **Mục đích:** Hiển thị dung lượng **tổng thể** của các hệ thống tệp (file system) đã được "mount" (gắn) vào hệ thống.
    * **Cách dùng phổ biến:** `df -h`
        * `-h` (human-readable): Hiển thị dung lượng dưới dạng dễ đọc (ví dụ: `1.2G` thay vì `12582912`).
    * **Khi nào dùng:** Khi bạn muốn biết "Cả ổ đĩa còn trống bao nhiêu?"
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ df -h
    Filesystem      Size  Used Avail Use% Mounted on
    tmpfs           1.6G  2.5M  1.6G   1% /run
    /dev/nvme0n1p4  296G   73G  210G  26% /
    tmpfs           7.8G   88M  7.7G   2% /dev/shm
    tmpfs           5.0M   12K  5.0M   1% /run/lock
    efivarfs        184K  167K   13K  94% /sys/firmware/efi/efivars
    /dev/nvme0n1p1   96M   37M   60M  39% /boot/efi
    tmpfs           1.6G  124K  1.6G   1% /run/user/1000
    ```
* **`du` (Disk Usage):**
    * **Mục đích:** Ước tính dung lượng mà các **tập tin (file) và thư mục (directory) cụ thể** đang chiếm dụng.
    * **Cách dùng phổ biến:** `du -sh /path/to/directory`
        * `-s` (summarize): Chỉ hiển thị tổng dung lượng của thư mục bạn chỉ định, không liệt kê từng file con.
        * `-h` (human-readable): Hiển thị dạng dễ đọc.
    * **Khi nào dùng:** Khi bạn muốn biết "Thư mục `Documents` này nặng bao nhiêu?"
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ du -sh ~/Documents/
    359M    /home/ngtukien/Documents/
    ```
* **`lsblk` (List Block Devices):**
    * **Mục đích:** Liệt kê tất cả các **thiết bị khối** (như ổ cứng, SSD, USB) và các phân vùng (partition) của chúng.
    * **Cách dùng:** Chỉ cần gõ `lsblk`.
    * **Khi nào dùng:** Khi bạn muốn xem cấu trúc vật lý của ổ đĩa, ví dụ ổ `sda` được chia thành `sda1`, `sda2` và chúng đang được "mount" ở đâu.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ lsblk
    NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
    loop0         7:0    0     4K  1 loop /snap/bare/5
    loop1         7:1    0  73.9M  1 loop /snap/core22/2139
    loop2         7:2    0  73.9M  1 loop /snap/core22/2133
    loop3         7:3    0 114.1M  1 loop /snap/discord/258
    loop4         7:4    0 114.1M  1 loop /snap/discord/257
    loop5         7:5    0  11.1M  1 loop /snap/firmware-updater/167
    loop6         7:6    0  18.5M  1 loop /snap/firmware-updater/210
    loop7         7:7    0   516M  1 loop /snap/gnome-42-2204/202
    loop8         7:8    0 516.2M  1 loop /snap/gnome-42-2204/226
    loop9         7:9    0  10.8M  1 loop /snap/snap-store/1270
    loop10        7:10   0  91.7M  1 loop /snap/gtk-common-themes/1535
    loop11        7:11   0  17.5M  1 loop /snap/snap-store/1300
    loop12        7:12   0  50.8M  1 loop /snap/snapd/25202
    loop13        7:13   0  50.9M  1 loop /snap/snapd/25577
    loop14        7:14   0   576K  1 loop /snap/snapd-desktop-integration/315
    nvme0n1     259:0    0 476.9G  0 disk 
    ├─nvme0n1p1 259:1    0   100M  0 part /boot/efi
    ├─nvme0n1p2 259:2    0    16M  0 part 
    ├─nvme0n1p3 259:3    0 174.7G  0 part 
    └─nvme0n1p4 259:4    0 301.3G  0 part /
    ```
### b. Bộ nhớ (Memory) và Thời gian chạy (Uptime)
* **`free`:**
    * **Mục đích:** Hiển thị dung lượng **RAM** và **Swap** (bộ nhớ ảo) đã sử dụng và còn trống.
    * **Cách dùng phổ biến:** `free -h`
    * **Lưu ý:** Cột "available" (khả dụng) thường quan trọng hơn cột "free" (trống), vì Linux dùng RAM trống để làm bộ đệm (cache). "Available" cho biết lượng RAM thực sự còn lại cho các ứng dụng mới.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ free -h
                   total        used        free      shared  buff/cache   available
    Mem:            15Gi       6.5Gi       3.1Gi       431Mi       6.5Gi       8.9Gi
    Swap:          4.0Gi          0B       4.0Gi
    ```
    * `Mem` : RAM
    * `Swap` : Bộ nhớ ảo trên ổ đĩa cứng
      * Đây là một không gian trên ổ cứng/SSD của bạn mà hệ điều hành "giả vờ" là RAM.
      * Khi RAM thật (Mem) bị đầy, hệ điều hành sẽ di chuyển những dữ liệu ít dùng từ RAM sang Swap để giải phóng RAM cho các tác vụ quan trọng hơn.
      * Nó giúp máy không bị "treo" (crash) khi hết RAM.
      * Swap chậm hơn rất nhiều so với RAM thật (vì ổ cứng chậm hơn RAM). Nếu máy phải dùng Swap nhiều, bạn sẽ thấy hệ thống bị chậm hoặc "lag".
* **`uptime`:**
    * **Mục đích:** Cho biết hệ thống đã chạy được bao lâu kể từ lần khởi động cuối cùng.
    * **Cách dùng:** Chỉ cần gõ `uptime` hoặc `uptime -p` để làm đẹp.
    * **Thông tin thêm:** Lệnh này cũng hiển thị "load average" (tải trung bình), một chỉ số quan trọng để xem máy chủ có đang bị quá tải hay không.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ uptime -p
    up 1 hour, 12 minutes
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ uptime
    14:16:33 up  1:12,  1 user,  load average: 0.78, 0.87, 0.82
    ```
    * `load average: 0.78, 0.87, 0.82` : Tải trung bình trong 1, 5, và 15 phút qua.
      * Đây là số lượng tiến trình đang hoạt động hoặc đang chờ CPU xử lý.
      * Ví dụ: Nếu bạn có 4 lõi CPU, thì tải trung bình dưới 4.0 là ổn. Trên 4.0 có thể cho thấy CPU đang quá tải.
### c. Thông tin Hệ thống và CPU
  * **`uname` (Unix Name):**
    * **Mục đích:** In ra thông tin cơ bản về hệ thống.
    * **Cách dùng phổ biến:** `uname -a` (all - tất cả)
    * **Thông tin:** Lệnh này cho bạn biết tên kernel (ví dụ: `Linux`), tên máy (hostname), phiên bản kernel, và kiến trúc (ví dụ: `x86_64`).
      ```shell
      ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ uname -a
      Linux NgTuKien 6.14.0-33-generic #33~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Fri Sep 19 17:02:30 UTC 2 x86_64 x86_64 x86_64 GNU/Linux
      ```
      * **Hệ điều hành:** `GNU/Linux`.
      * **Tên máy (Hostname):** `NgTuKien`.
      * **Kiến trúc:** `x86_64` (Bạn đang dùng hệ thống 64-bit).
      * **Phiên bản Kernel:** `6.14.0-33-generic` (Đây là "lõi" của hệ điều hành).
      * **Bản phân phối:** Kernel này được build cho `Ubuntu 24.04.1`.
      * **Hỗ trợ CPU:** `SMP` (Kernel hỗ trợ đa xử lý, tức là máy có nhiều lõi/CPU).
* **`lscpu` (List CPU):**
  * **Mục đích:** Hiển thị thông tin chi tiết về **CPU** của máy.
  * **Cách dùng:** Chỉ cần gõ `lscpu`.
  * **Thông tin:** Cho biết kiến trúc, model CPU, số lượng core (lõi), số lượng thread (luồng), kích thước bộ đệm (cache), v.v.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ lscpu
    Architecture:                x86_64
    CPU op-mode(s):            32-bit, 64-bit
    Address sizes:             39 bits physical, 48 bits virtual
    Byte Order:                Little Endian
    CPU(s):                      12
    On-line CPU(s) list:       0-11
    Vendor ID:                   GenuineIntel
    Model name:                11th Gen Intel(R) Core(TM) i5-11400H @ 2.70GHz
    CPU family:              6
    Model:                   141
    Thread(s) per core:      2
    Core(s) per socket:      6
    Socket(s):               1
    Stepping:                1
    CPU(s) scaling MHz:      23%
    CPU max MHz:             4500.0000
    CPU min MHz:             800.0000
    BogoMIPS:                5376.00
    Flags:                   fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp lm constant_t
    sc art arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf tsc_known_freq pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 sdbg fma
    cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3dnowprefetch cpuid_fault epb cat_l2 cdp_l2 ssb
    d ibrs ibpb stibp ibrs_enhanced tpr_shadow flexpriority ept vpid ept_ad fsgsbase tsc_adjust bmi1 avx2 smep bmi2 erms invpcid rdt_a avx512f avx512dq rdseed adx
    smap avx512ifma clflushopt clwb intel_pt avx512cd sha_ni avx512bw avx512vl xsaveopt xsavec xgetbv1 xsaves split_lock_detect user_shstk dtherm ida arat pln pts
    hwp hwp_notify hwp_act_window hwp_epp hwp_pkg_req vnmi avx512vbmi umip pku ospke avx512_vbmi2 gfni vaes vpclmulqdq avx512_vnni avx512_bitalg avx512_vpopcntdq r
    dpid movdiri movdir64b fsrm avx512_vp2intersect md_clear ibt flush_l1d arch_capabilities
    Virtualization features:     
    Virtualization:            VT-x
    Caches (sum of all):         
    L1d:                       288 KiB (6 instances)
    L1i:                       192 KiB (6 instances)
    L2:                        7.5 MiB (6 instances)
    L3:                        12 MiB (1 instance)
    NUMA:                        
    NUMA node(s):              1
    NUMA node0 CPU(s):         0-11
    ...
    ```
    * **Tên Model:** 11th Gen Intel(R) Core(TM) i5-11400H
    * **Kiến trúc:** `x86_64` (64-bit)
    * **Số lõi vật lý (Cores):** **6**
    * **Số luồng (Threads) / CPU logic:** **12** (Vì `Thread(s) per core: 2` - công nghệ Hyper-Threading)
    * **Tốc độ cơ bản:** 2.70GHz
    * **Tốc độ tối đa (Boost):** 4.50GHz
    * **Hỗ trợ ảo hóa:** **Có** (`VT-x`) - Đây là tính năng quan trọng để chạy máy ảo (VirtualBox, VMWare) và Docker hiệu quả.
    * **Bộ nhớ đệm L3:** 12 MiB (Đây là bộ nhớ cache lớn nhất, dùng chung cho cả 6 lõi để tăng tốc độ xử lý).
## 3. Dịch vụ và tiến trình nền (daemon)
Một **daemon** là một tiến trình chạy ngầm (background) để thực hiện các tác vụ hệ thống (ví dụ: máy chủ web `httpd`, máy chủ cơ sở dữ liệu `mysqld`).
### a. `systemctl`: Lệnh quản lý dịch vụ chính
`systemctl` là công cụ chính và hiện đại nhất để điều khiển `systemd`, hệ thống quản lý dịch vụ mặc định trên hầu hết các bản Linux mới (như Ubuntu 16.04+, CentOS 7+, v.v.).
* **`systemctl start <tên-dịch-vụ>`** : Khởi động một dịch vụ.
  ```shell
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
  ngtukien   13310  0.0  0.0   9144  2300 pts/0    S+   15:02   0:00 grep --color=auto docker
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl start docker
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
  root       13402  0.8  0.5 2586756 84552 ?       Ssl  15:02   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
  ngtukien   13761  0.0  0.0   9144  2208 pts/0    S+   15:03   0:00 grep --color=auto docker
  ```
* **`systemctl restart <tên-dịch-vụ>`** : Khởi động lại dịch vụ. Lệnh này hữu ích khi bạn vừa thay đổi file cấu hình và muốn áp dụng thay đổi.
  ```shell
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
  root       13402  0.8  0.5 2586756 84552 ?       Ssl  15:02   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
  ngtukien   13761  0.0  0.0   9144  2208 pts/0    S+   15:03   0:00 grep --color=auto docker
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl restart docker
  ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
  root       13863  6.0  0.5 2586500 84448 ?       Ssl  15:04   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
  ngtukien   14202  0.0  0.0   9144  2176 pts/0    S+   15:05   0:00 grep --color=auto docker
  ```
* **`systemctl stop <tên-dịch-vụ>`** : Dừng một dịch vụ đang chạy.
    ```
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
    root       13863  6.0  0.5 2586500 84448 ?       Ssl  15:04   0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
    ngtukien   14202  0.0  0.0   9144  2176 pts/0    S+   15:05   0:00 grep --color=auto docker
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl stop docker.socket docker.service
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ps aux | grep docker
    ngtukien   14382  0.0  0.0   9144  2236 pts/0    S+   15:07   0:00 grep --color=auto docker
    ```
* **`systemctl status <tên-dịch-vụ>`** : Dùng để xem trạng thái chi tiết của dịch vụ (đang chạy `active (running)`, đã dừng `inactive (dead)`, hay bị lỗi `failed`). Nó cũng hiển thị vài dòng log mới nhất.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl status docker
    ○ docker.service - Docker Application Container Engine
         Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; preset: enabled)
         Active: inactive (dead) since Thu 2025-10-30 15:07:05 +07; 2min 2s ago
       Duration: 2min 6.015s
    TriggeredBy: ○ docker.socket
           Docs: https://docs.docker.com
        Process: 13863 ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock (code=exited, status=0/SUCCESS)
       Main PID: 13863 (code=exited, status=0/SUCCESS)
            CPU: 911ms
    
    Oct 30 15:04:59 NgTuKien dockerd[13863]: time="2025-10-30T15:04:59.345552036+07:00" level=info msg="Completed buildkit initialization"
    Oct 30 15:04:59 NgTuKien dockerd[13863]: time="2025-10-30T15:04:59.353752362+07:00" level=info msg="Daemon has completed initialization"
    Oct 30 15:04:59 NgTuKien dockerd[13863]: time="2025-10-30T15:04:59.353841457+07:00" level=info msg="API listen on /run/docker.sock"
    Oct 30 15:04:59 NgTuKien systemd[1]: Started docker.service - Docker Application Container Engine.
    Oct 30 15:07:05 NgTuKien systemd[1]: Stopping docker.service - Docker Application Container Engine...
    Oct 30 15:07:05 NgTuKien dockerd[13863]: time="2025-10-30T15:07:05.369865724+07:00" level=info msg="Processing signal 'terminated'"
    Oct 30 15:07:05 NgTuKien dockerd[13863]: time="2025-10-30T15:07:05.372107472+07:00" level=info msg="stopping event stream following graceful shutdown" error="<nil>" module=libcontainerd n>
    Oct 30 15:07:05 NgTuKien dockerd[13863]: time="2025-10-30T15:07:05.372717924+07:00" level=info msg="Daemon shutdown complete"
    Oct 30 15:07:05 NgTuKien systemd[1]: docker.service: Deactivated successfully.
    Oct 30 15:07:05 NgTuKien systemd[1]: Stopped docker.service - Docker Application Container Engine.
    ```
* **`systemctl enable <tên-dịch-vụ>`** : Cho phép dịch vụ tự động khởi động cùng hệ thống khi bạn bật máy.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl enable docker 
    Synchronizing state of docker.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
    Executing: /usr/lib/systemd/systemd-sysv-install enable docker
    Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.
    ```
* **`systemctl disable <tên-dịch-vụ>`** : Ngăn không cho dịch vụ tự động khởi động cùng hệ thống.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo systemctl disable docker 
    Synchronizing state of docker.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
    Executing: /usr/lib/systemd/systemd-sysv-install disable docker
    Removed "/etc/systemd/system/multi-user.target.wants/docker.service".
    ```
### b. `journalctl`: Lệnh xem Log (Nhật ký)
`systemd` có một hệ thống ghi log tập trung gọi là `journald`. Lệnh `journalctl` dùng để đọc các log này. 
* **Cách dùng phổ biến:** : Dùng `journald` để đọc lỗi khi chạy 1 dịch vụ.
    * **`journalctl -u <tên-dịch-vụ>`**: Chỉ xem log của một dịch vụ (unit) cụ thể. 
    * **`journalctl -u docker -f`**: Xem log của Docker và **theo dõi trực tiếp** (live, giống `tail -f`).
    * **`journalctl -b`**: Xem tất cả log kể từ lần khởi động máy (`boot`) gần nhất.
```shell
ngtukien@NgTuKien:~$ journalctl -u docker
Oct 25 11:55:24 NgTuKien systemd[1]: Starting docker.service - Docker Applicati>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.037460042+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.038998878+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.039748865+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.039764288+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.039837759+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.087735625+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.109722460+07:>
Oct 25 11:55:25 NgTuKien dockerd[1509]: time="2025-10-25T11:55:25.320435656+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.026581933+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.026611116+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.026622206+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.126581262+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.126581259+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.140396265+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.140631130+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.152272339+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.152543458+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.287873646+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.291195269+07:>
Oct 25 11:55:26 NgTuKien dockerd[1509]: time="2025-10-25T11:55:26.291246265+07:>
Oct 25 11:55:26 NgTuKien systemd[1]: Started docker.service - Docker Applicatio>
Oct 25 11:55:40 NgTuKien systemd[1]: Stopping docker.service - Docker Applicati>
lines 1-23
```
### c. `service`: Lệnh cũ (Legacy)
* Đây là lệnh quản lý dịch vụ cũ (từ hệ thống `SysVinit`).
* **Cách dùng:** `sudo service <tên-dịch-vụ> <hành-động>`
```shell
ngtukien@NgTuKien:~$ service docker status
● docker.service - Docker Application Container Engine
     Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; preset: e>
     Active: active (running) since Sun 2025-11-02 09:24:20 +07; 58min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 1532 (dockerd)
      Tasks: 19
     Memory: 125.8M (peak: 130.5M)
        CPU: 925ms
     CGroup: /system.slice/docker.service
             └─1532 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/cont>

Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.123661331+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.140769967+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.339608065+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.782447317+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.793051609+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.793203901+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.945009139+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.947340859+07:>
Nov 02 09:24:20 NgTuKien dockerd[1532]: time="2025-11-02T09:24:20.947366867+07:>
Nov 02 09:24:20 NgTuKien systemd[1]: Started docker.service - Docker Applicatio>
lines 1-22/22 (END)
````
>**Lưu ý:** Trên các hệ thống dùng `systemd`, lệnh `service` thực chất chỉ là một "lớp vỏ" (wrapper) và khi bạn chạy, nó sẽ tự động **gọi lệnh `systemctl` tương ứng** ở bên dưới. Bạn nên tập dùng `systemctl` vì nó là tiêu chuẩn mới.
# Phần 6: Quản lý gói phần mềm
## 1. Trình quản lý gói (Package Manager)
Đây là một hệ thống tự động hóa việc **cài đặt**, **cập nhật**, **gỡ bỏ** phần mềm (được gọi là các "gói" - package).

Quan trọng nhất, nó tự động xử lý các **phụ thuộc (dependencies)**. Ví dụ, khi bạn muốn cài đặt chương trình A, nhưng A cần thư viện B và C để chạy, trình quản lý gói sẽ tự động cài cả A, B, và C cho bạn.

---
### a. Ubuntu/Debian: `apt` và `apt-get`
* **`apt-get`:**
    * Đây là công cụ truyền thống, mạnh mẽ và rất ổn định.
    * Nó thường được ưu tiên sử dụng trong các **script tự động** vì đầu ra (output) của nó nhất quán và dễ phân tích.
* **`apt`:**
    * Đây là công cụ **hiện đại và thân thiện hơn**, được giới thiệu sau này.
    * Nó kết hợp các tính năng hay dùng nhất của `apt-get` (để cài/gỡ) và `apt-cache` (để tìm kiếm).
    * Nó có giao diện đẹp hơn, có **thanh tiến trình (progress bar)**, và được thiết kế để người dùng tương tác trực tiếp.
> **Khuyến nghị:** Khi dùng hàng ngày trên terminal, bạn nên **ưu tiên dùng `apt`**.

---
### b.  CentOS/RedHat/Fedora: `yum` và `dnf`
* **`yum` (Yellowdog Updater, Modified):**
    * Là trình quản lý gói "truyền thống" của gia đình RedHat (ví dụ: trên CentOS 7). Nó tương đương với `apt-get`.
* **`dnf` (Dandified YUM):**
    * Đây là **phiên bản kế nhiệm** của `yum`. Nó là trình quản lý gói mặc định trên các hệ thống mới như Fedora, RHEL 8+, CentOS 8+.
    * `dnf` được viết lại để giải quyết các vấn đề của `yum`, với **tốc độ nhanh hơn** và khả năng **xử lý phụ thuộc tốt hơn**.
> **Khuyến nghị:** Nếu hệ thống của bạn hỗ trợ `dnf`, hãy **ưu tiên dùng `dnf`** thay vì `yum`.
## 2. Cài đặt và gỡ bỏ phần mềm
### a. Quy trình Cài đặt & Cập nhật
* `sudo apt update` : Đồng bộ hóa (làm mới) danh sách các gói phần mềm từ các máy chủ (repositories) về máy của bạn.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo apt update
    [sudo] password for ngtukien: 
    Hit:1 https://download.docker.com/linux/ubuntu noble InRelease
    Get:2 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]                                                                                                                  
    Hit:3 https://brave-browser-apt-release.s3.brave.com stable InRelease                                                                                                                      
    Hit:4 https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu noble InRelease                                                                                                   
    Get:5 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Packages [906 kB]                                                                             
    Get:6 https://packages.microsoft.com/repos/code stable InRelease [3,590 B]                                              
    Hit:7 http://us.archive.ubuntu.com/ubuntu noble InRelease                                                               
    Get:8 https://packages.microsoft.com/repos/code stable/main amd64 Packages [20.3 kB]
    Hit:9 http://us.archive.ubuntu.com/ubuntu noble-updates InRelease                        
    Hit:10 http://us.archive.ubuntu.com/ubuntu noble-backports InRelease                                  
    Get:11 http://security.ubuntu.com/ubuntu noble-security/universe Translation-en [203 kB]
    Fetched 1,259 kB in 4s (315 kB/s)             
    Reading package lists... Done
    ...
    ```
* `sudo apt upgrade` : Sau khi "check" menu bằng `update`, lệnh này sẽ **nâng cấp tất cả** các gói phần mềm bạn *đã cài* lên phiên bản mới nhất (nếu có).
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo apt upgrade
    Reading package lists... Done
    Building dependency tree... Done
    Reading state information... Done
    Calculating upgrade... Done
    The following NEW packages will be installed:
      linux-headers-6.14.0-34-generic linux-hwe-6.14-headers-6.14.0-34 linux-hwe-6.14-tools-6.14.0-34 linux-image-6.14.0-34-generic linux-modules-6.14.0-34-generic
      linux-modules-extra-6.14.0-34-generic linux-tools-6.14.0-34-generic
    The following packages will be upgraded:
      binutils binutils-common binutils-x86-64-linux-gnu brave-browser libbinutils libctf-nobfd0 libctf0 libgprofng0 libsframe1 linux-generic-hwe-24.04 linux-headers-generic-hwe-24.04
      linux-image-generic-hwe-24.04 linux-libc-dev linux-tools-common xserver-common xserver-xephyr xserver-xorg-core xserver-xorg-legacy xwayland
    19 upgraded, 7 newly installed, 0 to remove and 0 not upgraded.
    13 standard LTS security updates
    Need to get 331 MB of archives.
    After this operation, 293 MB of additional disk space will be used.
    Do you want to continue? [Y/n] Y
    Get:1 http://security.ubuntu.com/ubuntu noble-security/main amd64 libgprofng0 amd64 2.42-4ubuntu2.6 [849 kB]
    Get:2 http://us.archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-modules-6.14.0-34-generic amd64 6.14.0-34.34~24.04.1 [40.7 MB]
    ...
    ```
* `sudo apt install <tên-gói>` : Kiểm tra, tìm kiếm và cài đặt một gói phần mềm **mới**.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo apt install htop
    Reading package lists... Done
    Building dependency tree... Done
    Reading state information... Done
    The following NEW packages will be installed:
      htop
    0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
    Need to get 176 kB of archives.
    After this operation, 512 kB of additional disk space will be used.
    Get:1 http://us.archive.ubuntu.com/ubuntu noble/main amd64 htop amd64 3.2.1-1build1 [176 kB]
    Fetched 176 kB in 1s (296 kB/s)    
    Selecting previously unselected package htop.
    (Reading database ... 219456 files and directories currently installed.)
    Preparing to unpack .../htop_3.2.1-1build1_amd64.deb ...
    Unpacking htop (3.2.1-1build1) ...
    Setting up htop (3.2.1-1build1) ...
    Processing triggers
    ```
### b. Gỡ bỏ Phần mềm
* `sudo apt remove <tên-gói>` : Gỡ cài đặt một gói phần mềm.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo apt remove htop
    [sudo] password for ngtukien: 
    Reading package lists... Done
    Building dependency tree... Done
    Reading state information... Done
    The following packages were automatically installed and are no longer required:
      linux-headers-6.14.0-32-generic linux-hwe-6.14-headers-6.14.0-32 linux-hwe-6.14-tools-6.14.0-32 linux-image-6.14.0-32-generic linux-modules-6.14.0-32-generic
      linux-modules-extra-6.14.0-32-generic linux-tools-6.14.0-32-generic
    Use 'sudo apt autoremove' to remove them.
    The following packages will be REMOVED:
      htop
    0 upgraded, 0 newly installed, 1 to remove and 0 not upgraded.
    After this operation, 434 kB disk space will be freed.
    Do you want to continue? [Y/n] Y
    (Reading database ... 271260 files and directories currently installed.)
    Removing htop (3.3.0-4build1) ...
    
    Progress: [  0%] [......................................................................................................................................................................]   
    Progress: [ 33%] [#######################################################...............................................................................................................]   
    Processing triggers for hicolor-icon-theme (0.17-2) ...#########################################################################........................................................]   
    Processing triggers for gnome-menus (3.36.0-1.1ubuntu3) ...
    Processing triggers for man-db (2.12.0-4build2) ...
    Processing triggers for desktop-file-utils (0.27-2build1) ...
    ```
> **Lưu ý:** Lệnh này gỡ chương trình, nhưng **thường giữ lại các file cấu hình** của nó (phòng trường hợp bạn cài lại sau).

> **Mẹo bổ sung (Nên biết):**
>   * **`sudo apt purge <tên-gói>`**: Gỡ gói và **xóa luôn cả file cấu hình**. Đây là cách "gỡ sạch".
>   * **`sudo apt autoremove`**: Dọn dẹp các gói phụ thuộc (dependencies) mà đã được cài tự động nhưng giờ không còn gói nào cần đến chúng nữa.
### c. Kiểm tra Gói đã cài đặt
* `dpkg` là trình quản lý gói "cấp thấp" (thằng `apt` gọi nó ở bên dưới). Lệnh `dpkg -l` (list) sẽ **liệt kê TẤT CẢ** các gói đã được cài đặt trên hệ thống của bạn.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ dpkg -l
    Desired=Unknown/Install/Remove/Purge/Hold
    | Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
    |/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
    ||/ Name                                             Version                                   Architecture Description
    +++-================================================-=========================================-============-================================================================================
    ii  accountsservice                                  23.13.9-2ubuntu6                          amd64        query and manipulate user account information
    ii  acl                                              2.3.2-1build1.1                           amd64        access control list - utilities
    ii  adduser                                          3.137ubuntu1                              all          add and remove users and groups
    ii  adwaita-icon-theme                               46.0-1                                    all          default icon theme of GNOME
    ii  alsa-base                                        1.0.25+dfsg-0ubuntu7                      all          ALSA driver configuration files
    ii  alsa-topology-conf                               1.2.5.1-2                                 all          ALSA topology configuration files
    ii  alsa-ucm-conf                                    1.2.10-1ubuntu5.7                         all          ALSA Use Case Manager configuration files
    
    ```
## 3. Tạo và sử dụng alias
* Đôi khi, các lệnh quản lý gói khá dài dòng (ví dụ: `sudo apt update && sudo apt upgrade -y`). Để tiết kiệm thời gian, bạn có thể tạo các **alias** (bí danh) trong file `~/.bashrc` hoặc `~/.zshrc`.
* Ví dụ, bạn có thể thêm dòng sau vào `~/.bashrc`:
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo "alias ll='ls -alF'" >> ~/bashrc
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ cat ~/bashrc | grep "alias ll='ls -alF'"
    alias ll='ls -alF'
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ll .
    total 24
    drwxrwxr-x 5 ngtukien ngtukien 4096 Oct 30 10:17 ./
    drwxrwxr-x 5 ngtukien ngtukien 4096 Oct 27 13:55 ../
    drwxrwxr-x 8 ngtukien ngtukien 4096 Oct 30 10:12 .git/
    -rw-rw-r-- 1 ngtukien ngtukien   27 Oct 30 10:11 .gitignore
    drwxrwxr-x 2 ngtukien ngtukien 4096 Oct 30 18:13 .idea/
    drwxrwxr-x 4 ngtukien ngtukien 4096 Oct 30 10:11 kiennt_b23dccn465_training_gd1/
    ```
# Phần 7: Làm việc với mạng (Networking)
## 1. Kiểm tra mạng
### a. Kiểm tra kết nối
* `ping` : Gửi một gói tin nhỏ (ICMP ECHO_REQUEST) đến một máy chủ và đợi nó phản hồi để kiểm tra xem máy chủ còn sống hay không, độ trễ của máy chủ. Để ngát, ta nhấn tổ hợp `Ctrl C`.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ping facebook.com
    PING facebook.com (2a03:2880:f15e:83:face:b00c:0:25de) 56 data bytes
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=1 ttl=54 time=26.3 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=2 ttl=54 time=27.7 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=3 ttl=54 time=26.6 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=4 ttl=54 time=28.6 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=5 ttl=54 time=28.8 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=6 ttl=54 time=26.9 ms
    64 bytes from edge-star-mini6-shv-01-hkg4.facebook.com (2a03:2880:f15e:83:face:b00c:0:25de): icmp_seq=7 ttl=54 time=28.7 ms
    ^C
    --- facebook.com ping statistics ---
    7 packets transmitted, 7 received, 0% packet loss, time 6011ms
    rtt min/avg/max/mdev = 26.327/27.656/28.752/0.973 ms
    ```
### b. Cấu hình IP
* `ifconfig` (Interface Configuration): Xem cấu hình các giao diện mạng.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ifconfig
    br-17f1a29b938a: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
    inet 172.18.0.1  netmask 255.255.0.0  broadcast 172.18.255.255
    ether 9a:7d:b7:e2:f6:ac  txqueuelen 0  (Ethernet)
    RX packets 0  bytes 0 (0.0 B)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 0  bytes 0 (0.0 B)
    TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    br-1cddd2ec6b6b: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
    inet 172.19.0.1  netmask 255.255.0.0  broadcast 172.19.255.255
    ether e2:fd:94:a0:83:33  txqueuelen 0  (Ethernet)
    RX packets 0  bytes 0 (0.0 B)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 0  bytes 0 (0.0 B)
    TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    br-dcc3b563a5df: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
    inet 172.20.0.1  netmask 255.255.0.0  broadcast 172.20.255.255
    ether 8e:0b:f6:2b:79:6e  txqueuelen 0  (Ethernet)
    RX packets 0  bytes 0 (0.0 B)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 0  bytes 0 (0.0 B)
    TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    docker0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
    inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
    ether 9a:d4:59:22:88:99  txqueuelen 0  (Ethernet)
    RX packets 0  bytes 0 (0.0 B)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 0  bytes 0 (0.0 B)
    TX errors 0  dropped 30 overruns 0  carrier 0  collisions 0
    
    enp3s0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
    ether 08:8f:c3:46:57:e0  txqueuelen 1000  (Ethernet)
    RX packets 0  bytes 0 (0.0 B)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 0  bytes 0 (0.0 B)
    TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
    inet 127.0.0.1  netmask 255.0.0.0
    inet6 ::1  prefixlen 128  scopeid 0x10<host>
    loop  txqueuelen 1000  (Local Loopback)
    RX packets 6500  bytes 2741014 (2.7 MB)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 6500  bytes 2741014 (2.7 MB)
    TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    wlp0s20f3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
    inet 192.168.1.241  netmask 255.255.255.0  broadcast 192.168.1.255
    inet6 fe80::8e:8a19:f760:5c4b  prefixlen 64  scopeid 0x20<link>
    inet6 2402:800:61cd:da7b:7964:b235:ebad:c2fa  prefixlen 64  scopeid 0x0<global>
    inet6 2402:800:61cd:da7b:bddf:aa38:5bb9:1c3a  prefixlen 64  scopeid 0x0<global>
    ether 88:d8:2e:5f:05:ff  txqueuelen 1000  (Ethernet)
    RX packets 1031806  bytes 1309601236 (1.3 GB)
    RX errors 0  dropped 0  overruns 0  frame 0
    TX packets 154590  bytes 29773539 (29.7 MB)
    TX errors 0  dropped 36 overruns 0  carrier 0  collisions 0
    ```
  * Kết nối chính (Card Wifi)
    * **Tên thiết bị:** `wlp0s20f3`
    * **Ý nghĩa:** Tên `wlp...` (Wireless LAN) cho biết đây là **card Wifi** của bạn.
    * **Địa chỉ IP (IPv4):** **`192.168.1.241`**. Đây là địa chỉ IP của máy bạn trong mạng nội bộ (mạng LAN/Wifi ở nhà hoặc văn phòng).
    * **Địa chỉ IP (IPv6):** Máy bạn cũng có các địa chỉ IPv6 (hai dòng `inet6 2402:800:...`).
    * **Bằng chứng:** Đây là giao diện duy nhất có **lưu lượng truy cập (traffic)** đáng kể (`RX packets 65338`... `TX packets 21623...`). Điều này xác nhận bạn đang dùng Wifi để kết nối mạng.
  * **`enp3s0`:**
    * Đây là **card mạng có dây (Ethernet)** của bạn.
    * Nó đang ở trạng thái `UP` (bật) nhưng **không có địa chỉ IP** (`inet`). Điều này có nghĩa là card mạng vẫn hoạt động, nhưng bạn *không cắm dây mạng* vào.
  * **`docker0` và `br-...` (ví dụ `br-17f1a29b938a`):**
    * Đây là các **mạng ảo (virtual networks)**.
    * Chúng được **Docker** tạo ra để các container của bạn có thể giao tiếp với nhau và với máy chủ.
    * Các địa chỉ IP như `172.17.0.1`, `172.18.0.1`, v.v., là các cổng (gateway) cho các mạng ảo này, *không phải* IP thật của máy bạn.
  * **`lo` (Loopback):**
    * Đây là giao diện "nội bộ" của máy, luôn có địa chỉ là **`127.0.0.1`** (còn gọi là `localhost`).
    * Nó được dùng để các chương trình trên máy tự giao tiếp với nhau.
* `ip addr` (hoặc `ip a`) (IP Address) : Lệnh hiện đại hơn `ifconfig`, cung cấp thông tin chi tiết về các giao diện mạng.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ip a
    1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
    valid_lft forever preferred_lft forever
    2: enp3s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 08:8f:c3:46:57:e0 brd ff:ff:ff:ff:ff:ff
    3: wlp0s20f3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 88:d8:2e:5f:05:ff brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.241/24 brd 192.168.1.255 scope global dynamic noprefixroute wlp0s20f3
    valid_lft 10401sec preferred_lft 10401sec
    inet6 2402:800:61cd:da7b:7964:b235:ebad:c2fa/64 scope global temporary dynamic
    valid_lft 86284sec preferred_lft 82136sec
    inet6 2402:800:61cd:da7b:bddf:aa38:5bb9:1c3a/64 scope global dynamic mngtmpaddr noprefixroute
    valid_lft 86284sec preferred_lft 86284sec
    inet6 fe80::8e:8a19:f760:5c4b/64 scope link noprefixroute
    valid_lft forever preferred_lft forever
    4: br-17f1a29b938a: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether 9a:7d:b7:e2:f6:ac brd ff:ff:ff:ff:ff:ff
    inet 172.18.0.1/16 brd 172.18.255.255 scope global br-17f1a29b938a
    valid_lft forever preferred_lft forever
    5: br-1cddd2ec6b6b: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether e2:fd:94:a0:83:33 brd ff:ff:ff:ff:ff:ff
    inet 172.19.0.1/16 brd 172.19.255.255 scope global br-1cddd2ec6b6b
    valid_lft forever preferred_lft forever
    6: br-dcc3b563a5df: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether 8e:0b:f6:2b:79:6e brd ff:ff:ff:ff:ff:ff
    inet 172.20.0.1/16 brd 172.20.255.255 scope global br-dcc3b563a5df
    valid_lft forever preferred_lft forever
    7: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether 9a:d4:59:22:88:99 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
    valid_lft forever preferred_lft forever
    ```
### c. Xem kết nối
* `netstat` (Network Statistics): Hiển thị các kết nối mạng hiện tại, bảng định tuyến, thống kê giao diện mạng và các cổng (port) đang lắng nghe.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ netstat
    Active Internet connections (w/o servers)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State      
    tcp        0      0 NgTuKien:58350          lb-140-82-114-21-:https ESTABLISHED
    tcp        0      0 NgTuKien:58952          lb-140-82-114-21-:https ESTABLISHED
    tcp        0      0 NgTuKien:51706          52.175.140.176:https    TIME_WAIT  
    tcp        0      0 NgTuKien:52238          server-13-227-227:https ESTABLISHED
    tcp6       0      0 NgTuKien:48018          ec2-52-16-198-47.:https TIME_WAIT  
    tcp6       0      0 NgTuKien:35218          nchkga-ao-in-x0a.:https ESTABLISHED
    tcp6       0      0 NgTuKien:45308          edge-dgw6-shv-01-:https ESTABLISHED
    tcp6       0      0 NgTuKien:46788          edge-star6-shv-01:https ESTABLISHED
    udp        0      0 NgTuKien:bootpc         _gateway:bootps         ESTABLISHED
    udp6       0      0 NgTuKien:38649          hkg07s01-in-x0e.1:https ESTABLISHED
    udp6       0      0 NgTuKien:40293          nchkga-ab-in-x0a.:https ESTABLISHED
    udp6       0      0 NgTuKien:41235          nchkga-ab-in-x0a.:https ESTABLISHED
    Active UNIX domain sockets (w/o servers)
    Proto RefCnt Flags       Type       State         I-Node   Path
    unix  3      [ ]         STREAM     CONNECTED     29011    
    unix  3      [ ]         STREAM     CONNECTED     27674    /run/user/1000/bus
    unix  3      [ ]         STREAM     CONNECTED     18865    /run/systemd/journal/stdout
    unix  3      [ ]         STREAM     CONNECTED     19620    
    unix  3      [ ]         STREAM     CONNECTED     9817     
    unix  3      [ ]         STREAM     CONNECTED     24752    
    unix  3      [ ]         STREAM     CONNECTED     23833    
    unix  3      [ ]         STREAM     CONNECTED     61967    
    unix  3      [ ]         STREAM     CONNECTED     32449    
    unix  3      [ ]         STREAM     CONNECTED     19256    
    unix  3      [ ]         STREAM     CONNECTED     17093    
    ```
  * **`Proto` (Protocol):** Giao thức được sử dụng. Thường là `tcp` (cho IPv4), `tcp6` (cho IPv6), `udp` (cho IPv4), hoặc `udp6` (cho IPv6). 
    > Các socket UNIX (dòng dưới cùng) dùng để giao tiếp nội bộ trên máy, không qua mạng.
  * **`Recv-Q` (Receive Queue):** Hàng đợi nhận. Đây là lượng dữ liệu (tính bằng byte) đã được nhận từ phía máy chủ (`Foreign Address`) nhưng *chưa được chương trình trên máy bạn đọc* (`Local Address`). Nếu con số này lớn, có thể chương trình của bạn đang bị treo hoặc xử lý chậm.
  * **`Send-Q` (Send Queue):** Hàng đợi gửi. Đây là lượng dữ liệu (tính bằng byte) mà chương trình của bạn đã gửi đi nhưng *chưa nhận được xác nhận (ACK) từ máy chủ*. Nếu con số này lớn, có thể do mạng chậm hoặc máy chủ bên kia xử lý chậm.
    > **Lưu ý:** Cả `Recv-Q` và `Send-Q` ở trạng thái `ESTABLISHED` lý tưởng nên là **0**.
  * **`Local Address` (Địa chỉ cục bộ):** Địa chỉ IP và cổng (port) **trên máy của bạn** đang tham gia vào kết nối. Ví dụ: `NgTuKien:58350` (máy `NgTuKien`, cổng 58350) hoặc `localhost:63342`.
  * **`Foreign Address` (Địa chỉ ngoài):** Địa chỉ IP và cổng (port) của **máy chủ bên ngoài** mà bạn đang kết nối. Ví dụ: `server-13-227-227:https` (máy chủ `server-13...`, cổng `https`).
  * **`State` (Trạng thái):** Trạng thái hiện tại của kết nối (chủ yếu cho TCP).
    * **`ESTABLISHED`**: Kết nối đang diễn ra bình thường.
    * **`TIME_WAIT`**: Kết nối đã được đóng, nhưng hệ thống đang chờ một lúc để dọn dẹp.
    * **`CLOSE_WAIT`**: Phía bên kia đã ngắt kết nối, nhưng máy của bạn chưa đóng.
    * **`LISTEN`**: (Bạn sẽ thấy nếu dùng cờ `-l`) Dịch vụ đang "lắng nghe" chờ kết nối mới.
  * **`RefCnt` (Reference Count):** : Số lượng tiến trình (process) đang "giữ" hoặc "kết nối" đến socket này.
  * **`Flags`:** : Các cờ (flags) nội bộ của kernel, thường không quan trọng với người dùng thông thường.
  * **`Type` (Loại socket):** : Đây là một cột quan trọng, cho biết cách dữ liệu được truyền đi:
    * **`STREAM`**: Kiểu kết nối tin cậy (giống TCP). Dữ liệu được đảm bảo đến đúng thứ tự. Ví dụ phổ biến là `/var/run/docker.sock`.
    * **`DGRAM`**: Kiểu kết nối không tin cậy (giống UDP). Dữ liệu được gửi nhanh, không đảm bảo thứ tự. Ví dụ: Dịch vụ ghi log.
  * **`State` (Trạng thái):**
    * **`CONNECTED`**: Socket đang được kết nối.
    * **`LISTENING`**: (Bạn sẽ thấy nếu dùng cờ `-l`) Socket đang ở chế độ "lắng nghe", chờ tiến trình khác kết nối đến.
    * **`DISCONNECTED`**: Không có kết nối.
  * **`I-Node` (Inode Number):** : Mã định danh (ID) duy nhất của socket trên hệ thống file. Đây là một chi tiết kỹ thuật cấp thấp.
  * **`Path` (Đường dẫn):** : **Đây là cột quan trọng nhất.** Thay vì dùng địa chỉ IP và cổng (port), các socket UNIX sử dụng một **đường dẫn file trên ổ cứng** để làm "địa chỉ".
      * Ví dụ: Khi Docker CLI muốn nói chuyện với Docker daemon, nó sẽ kết nối đến file tại `/var/run/docker.sock`.
* `ss` (Socket Statistics): Tương tự với `netstat` nhưng nhanh hơn và cung cấp nhiều thông tin chi tiết hơn.
  * Ví dụ: `ss -tupl` (`-t`: TCP, `-u`: UDP, `-p`: Port, `-l`: Listening)
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ss -tulp
    Netid       State        Recv-Q       Send-Q                                     Local Address:Port                Peer Address:Port       Process                                          
    udp         UNCONN       0            0                                            224.0.0.251:5353                     0.0.0.0:*           users:(("brave",pid=3675,fd=78))                
    udp         UNCONN       0            0                                            224.0.0.251:5353                     0.0.0.0:*           users:(("brave",pid=3591,fd=178))               
    udp         UNCONN       0            0                                                0.0.0.0:5353                     0.0.0.0:*                                                           
    udp         UNCONN       0            0                                             127.0.0.54:53                       0.0.0.0:*                                                           
    udp         UNCONN       0            0                                          127.0.0.53%lo:53                       0.0.0.0:*                                                           
    udp         UNCONN       0            0                                                0.0.0.0:60645                    0.0.0.0:*                                                           
    udp         UNCONN       0            0                                                   [::]:5353                        [::]:*                                                           
    udp         UNCONN       0            0                                                   [::]:49239                       [::]:*                                                           
    udp         UNCONN       0            0                    [fe80::8e:8a19:f760:5c4b]%wlp0s20f3:546                         [::]:*                                                           
    tcp         LISTEN       0            4096                                           127.0.0.1:631                      0.0.0.0:*                                                           
    tcp         LISTEN       0            4096                                          127.0.0.54:53                       0.0.0.0:*                                                           
    tcp         LISTEN       0            4096                                       127.0.0.53%lo:53                       0.0.0.0:*                                                           
    tcp         LISTEN       0            4096                                  [::ffff:127.0.0.1]:42287                          *:*           users:(("embeddings-serv",pid=4504,fd=5))       
    tcp         LISTEN       0            511                                                    *:80                             *:*                                                           
    tcp         LISTEN       0            4096                                  [::ffff:127.0.0.1]:63342                          *:*           users:(("java",pid=3527,fd=63))                 
    tcp         LISTEN       0            4096                                               [::1]:631                         [::]:*     
    ```
### c. Tải dữ liệu
* `wget` (World Wide Web Get) : một trình tải xuống mạnh mẽ và đáng tin cậy với các chức năng chính
  * Tải tài liệu và đổi tên file (`-O`):**
    ```shell 
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ wget -O test.pdf https://pub-22372782169343468b196215da8acf5d.r2.dev/stemhub/documents/2025-10-21-4.%20quan%20ly%20tien%20trinh%20%5Bautosaved%5D%20-%20copy.pdf
    --2025-10-31 18:11:05--  https://pub-22372782169343468b196215da8acf5d.r2.dev/stemhub/documents/2025-10-21-4.%20quan%20ly%20tien%20trinh%20%5Bautosaved%5D%20-%20copy.pdf
    Resolving pub-22372782169343468b196215da8acf5d.r2.dev (pub-22372782169343468b196215da8acf5d.r2.dev)... 2606:4700:3117::6812:3222, 2606:4700:3113::6812:362d, 104.18.54.45, ...
    Connecting to pub-22372782169343468b196215da8acf5d.r2.dev (pub-22372782169343468b196215da8acf5d.r2.dev)|2606:4700:3117::6812:3222|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 2810898 (2.7M) [application/pdf]
    Saving to: ‘test.pdf’
    
    test.pdf                                       100%[====================================================================================================>]   2.68M  5.34MB/s    in 0.5s    
    
    2025-10-31 18:11:06 (5.34 MB/s) - ‘test.pdf’ saved [2810898/2810898]
    ```
* `curl` : là một công cụ cực kỳ linh hoạt để truyền dữ liệu đến hoặc từ một máy chủ, hỗ trợ rất nhiều giao thức (HTTP, HTTPS, FTP, FTPS, SCP, SMTP, v.v.).
  * **Test API:** Đây là công dụng phổ biến nhất của `curl`. Bạn có thể gửi các yêu cầu `GET`, `POST`, `PUT`, `DELETE` để kiểm tra các điểm cuối (endpoint) của API.
  * **In ra Standard Output (stdout):** Mặc định in kết quả ra màn hình. Điều này rất hữu ích để "nối" (pipe) đầu ra vào các lệnh khác (như `grep`, `jq`).
  * **Hỗ trợ nhiều giao thức:** Vượt xa `wget`, `curl` có thể xử lý email (SMTP), SSH (SCP), và nhiều giao thức khác.
  * **Gửi dữ liệu:** Dễ dàng gửi dữ liệu (ví dụ: JSON, data từ form) lên máy chủ.
  * **Xem Headers:** Dễ dàng lấy và hiển thị các header HTTP.
```shell 
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ curl -s  http://localhost:8080/ | head -5
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ curl -X POST http://localhost:8080/api/v1/auth/login -H "Content-Type: application/json" -d '{"username":"admin", "password":"Kien#123"}'
{"token":"eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImlhdCI6MTc2MTkxMTM1MywiZXhwIjoxNzYxOTk3NzUzfQ.s60mWtXjUQyM_8otUX9t-pm8Amt9VsX7-G9l0o-dm2s"}
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ curl -X GET http://localhost:8080/api/v1/auth/me -H "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImlhdCI6MTc2MTkxMTM1MywiZXhwIjoxNzYxOTk3NzUzfQ.s60mWtXjUQyM_8otUX9t-pm8Amt9VsX7-G9l0o-dm2s"
{"fullname":"Nguyễn Tự Kiên","userId":"714b1e90-4cac-45e2-b699-ffad8ade067b","username":"admin"}
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ curl -I http://localhost:8080/
HTTP/1.1 200 
X-Content-Type-Options: nosniff
X-XSS-Protection: 0
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Pragma: no-cache
Expires: 0
X-Frame-Options: DENY
Content-Type: text/html;charset=UTF-8
Content-Language: en-US
Date: Fri, 31 Oct 2025 11:53:53 GMT
```
## 2. Kết nối SSH và truyền file
**SSH** là viết tắt của **Secure Shell** (Vỏ Bảo Mật).

Đây là một **giao thức mạng** (một bộ quy tắc) cho phép bạn **kết nối và điều khiển một máy tính khác từ xa** (ví dụ như một máy chủ) một cách **an toàn tuyệt đối**.

### Mục đích chính

* **Đăng nhập từ xa (Remote Login):** Đây là công dụng phổ biến nhất. Bạn dùng lệnh `ssh user@ip` để mở một cửa sổ dòng lệnh (terminal) trên máy chủ. Từ đó, bạn có thể gõ lệnh và quản trị máy chủ y như đang ngồi trực tiếp trước nó.
* **Truyền file an toàn (Secure File Transfer):** SSH là nền tảng cho các công cụ như `scp` và `rsync`, cho phép bạn sao chép file giữa máy của mình và máy chủ một cách an toàn.
* **Thay thế các giao thức cũ, không an toàn:** SSH ra đời để thay thế `telnet`, một giao thức cũ gửi mật khẩu và dữ liệu dưới dạng **văn bản thuần** (không mã hóa), rất dễ bị đánh cắp.
### a. Kết nối và Truyền File (Các lệnh chính)
* **`ssh user@ip`** (Secure Shell) 
    * **Công dụng:** Đây là lệnh cơ bản nhất để **đăng nhập** và **điều khiển** một máy chủ từ xa một cách an toàn (mã hóa).
    * **Giống như:** Mở một cửa sổ Terminal trực tiếp trên máy chủ đó.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ssh -i ~/Downloads/stemhub.pem ubuntu@13.212.157.223
    The authenticity of host '13.212.157.223 (13.212.157.223)' can't be established.
    ED25519 key fingerprint is SHA256:p1biI5LphvndYdputMdEW07kbVu2pdnmxVuaN+ppYn8.
    This key is not known by any other names.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added '13.212.157.223' (ED25519) to the list of known hosts.
    @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
    @         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
    @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
    Permissions 0664 for '/home/ngtukien/Downloads/stemhub.pem' are too open.
    It is required that your private key files are NOT accessible by others.
    This private key will be ignored.
    Load key "/home/ngtukien/Downloads/stemhub.pem": bad permissions
    ubuntu@13.212.157.223: Permission denied (publickey).
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ sudo chmod 400 ~/Downloads/stemhub.pem
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ssh -i ~/Downloads/stemhub.pem ubuntu@13.212.157.223
    Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)
    
    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/pro
    
    System information as of Sat Nov  1 03:18:19 UTC 2025
    
    System load:  0.48              Temperature:           -273.1 C
    Usage of /:   26.5% of 6.71GB   Processes:             114
    Memory usage: 23%               Users logged in:       0
    Swap usage:   0%                IPv4 address for ens5: 172.31.10.74
    
    
    Expanded Security Maintenance for Applications is not enabled.
    
    0 updates can be applied immediately.
    
    Enable ESM Apps to receive additional future security updates.
    See https://ubuntu.com/esm or run: sudo pro status
    
    
    The list of available updates is more than a week old.
    To check for new updates run: sudo apt update
    
    Last login: Sat Nov  1 02:53:53 2025 from 3.0.5.37
    To run a command as administrator (user "root"), use "sudo <command>".
    See "man sudo_root" for details.
    
    ubuntu@ip-172-31-10-74:~$
    ```
* **`scp`** (Secure Copy) 
    * **Công dụng:** Dùng để **sao chép file/thư mục** giữa máy của bạn và máy chủ qua SSH.
    * **Giống như:** Lệnh `cp` (copy) nhưng hoạt động qua mạng.
    * *Ví dụ: `scp file.txt user@ip:/home/user/` (đẩy file lên) hoặc `scp user@ip:/home/user/file.txt .` (kéo file về).*
* **`rsync`** (Remote Sync) 
    * **Công dụng:** Dùng để **đồng bộ hóa** file và thư mục.
    * **Điểm mạnh:** Nó "thông minh" hơn `scp`. Nó chỉ truyền những phần (delta) của file đã bị thay đổi, chứ không chép đè toàn bộ file.
    * **Kết quả:** **Nhanh hơn `scp` rất nhiều** khi bạn cập nhật file thường xuyên (ví dụ: backup, deploy code).
### b. Thiết lập Đăng nhập không Mật khẩu (SSH Keys)
Mục đích là để đăng nhập vào máy chủ mà không cần gõ mật khẩu, vừa tiện lợi vừa an toàn hơn nhiều.
* **`ssh-keygen`** 
    * **Công dụng:** **Tạo ra một cặp "chìa khóa"** (key pair) trên máy của bạn (máy client).
    * **Kết quả:** Tạo ra 2 file:
        * `~/.ssh/id_rsa`: **Private Key (Chìa khóa riêng)**. Phải giữ bí mật tuyệt đối trên máy bạn.
        * `~/.ssh/id_rsa.pub`: **Public Key (Chìa khóa công khai)**. Đây là "ổ khóa" bạn sẽ gửi cho các máy chủ.
* **`ssh-copy-id user@ip`** 
    * **Công dụng:** **Cài đặt "ổ khóa"** (public key) của bạn lên máy chủ một cách tự động và an toàn.
    * **Cách hoạt động:** Nó đăng nhập vào máy chủ (lần cuối cùng dùng mật khẩu), tìm đến file `~/.ssh/authorized_keys` và dán public key của bạn vào đó.
**Kết quả cuối cùng:** Sau khi chạy `ssh-copy-id`, lần tiếp theo bạn gõ `ssh user@ip`, máy chủ sẽ nhận ra "ổ khóa" khớp với "chìa khóa riêng" bạn đang giữ và cho bạn vào thẳng mà không hỏi mật khẩu.
## 3. Kiểm tra cổng và filewall
### a. Công cụ Quản lý Firewall (Tường lửa)
Đây là các công cụ dùng để **cấu hình, bật, tắt, và kiểm tra các quy tắc (rules)** của tường lửa.
* **`iptables`** 
    * Đây là công cụ firewall **truyền thống, cốt lõi** và cực kỳ mạnh mẽ của Linux, hoạt động ở cấp độ kernel.
    * **Nhược điểm:** Nó rất phức tạp và khó sử dụng, cú pháp dài dòng.
    * **Giống như:** Bảng điều khiển điện chính của cả tòa nhà.
    * Câu lệnh phổ biến :
      * **`sudo iptables -L -n -v`**: **Xem trạng lthái** (Lệnh quan trọng nhất).
      * **`sudo iptables -A INPUT ... -j ACCEPT`**: **Thêm** quy tắc CHẤP NHẬN.
      * **`sudo iptables -A INPUT ... -j DROP`**: **Thêm** quy tắc CHẶN (thả gói tin).
      * **`sudo iptables -D INPUT [số]`**: **Xóa** quy tắc theo số dòng (xem số bằng `iptables -L --line-numbers`).
      * **`sudo iptables -F`**: **(Flush)** Xóa sạch *tất cả* quy tắc (Cẩn thận!).
* **`ufw` (Uncomplicated Firewall)** 
    * Đây là một giao diện **thân thiện, đơn giản hóa** để quản lý `iptables`.
    * **Ưu điểm:** Dễ học và dễ dùng cho các tác vụ phổ biến (ví dụ: `ufw allow 22`, `ufw status`).
    * **Giống như:** Cái công tắc đèn trong phòng. Nó điều khiển `iptables` một cách dễ dàng. Đây là công cụ được khuyên dùng trên Ubuntu.
    * 1 số câu lệnh thường dùng : 
      * **`sudo ufw status numbered`**: **Xem trạng thái** (và lấy số thứ tự để xóa).
      * **`sudo ufw enable`**: **Bật** tường lửa (Nhớ chạy `sudo ufw allow 22` trước nếu đang SSH!).
      * **`sudo ufw disable`**: **Tắt** tường lửa.
      * **`sudo ufw allow [cổng]`**: **Cho phép** một cổng (ví dụ: `sudo ufw allow 22`).
      * **`sudo ufw deny [cổng]`**: **Chặn** một cổng.
      * **`sudo ufw delete [số]`**: **Xóa** một quy tắc theo số thứ tự.
### b. Công cụ Kiểm tra Cổng (Port)
Công cụ này dùng để **xem** những cổng nào đang "mở" và "lắng nghe" kết nối trên máy của bạn.
* **`ss -tuln`** 
    * **Công dụng:** Liệt kê tất cả các "ổ cắm" (sockets) đang lắng nghe. Nó **không** cấu hình firewall, nó chỉ **hiển thị trạng thái**.
    * **Giải thích lệnh:**
        * `s` (socket): Hiển thị thông tin về socket.
        * `t`: Hiển thị cổng **T**CP.
        * `u`: Hiển thị cổng **U**DP.
        * `l`: Chỉ hiển thị các cổng đang **L**istening (lắng nghe).
        * `n`: Hiển thị dạng số (**n**umeric), không dịch sang tên (vídụ: 80 thay vì http) để chạy nhanh hơn.
> Để một người bên ngoài kết nối được với bạn, dịch vụ phải đang chạy (kiểm tra bằng `ss`) VÀ firewall phải cho phép (kiểm tra bằng `ufw`).
# Phần 8: Script & Automation cơ bản
## 1. Shell Script là gì
**Shell Script** là một tệp văn bản chứa một loạt các lệnh (commands) dành cho Unix shell (như Bash, Zsh). Thay vì gõ từng lệnh một cách thủ công vào terminal, bạn viết chúng vào một tệp để thực thi tuần tự.
Mục đích chính của nó là để **tự động hóa các tác vụ** lặp đi lặp lại.
### a. Tệp `.sh`
* Đây là phần mở rộng tệp (file extension) theo quy ước, viết tắt của "shell".
* Về mặt kỹ thuật, một shell script trong Linux không bắt buộc phải có đuôi `.sh` (hoặc bất kỳ đuôi nào) để hoạt động.
* Tuy nhiên, việc sử dụng `.sh` (ví dụ: `my_script.sh`) là một thông lệ tốt để giúp người dùng và hệ điều hành **nhận diện ngay lập tức** đây là một tệp script có thể thực thi.
### b. Cú pháp `#!/bin/bash` (Shebang)
  * Đây được gọi là **Shebang** (hoặc "hashbang").
  * Nó **bắt buộc phải là dòng đầu tiên** của tệp.
  * Nó chỉ định trình thông dịch (interpreter) nào sẽ được sử dụng để đọc và thực thi các lệnh bên dưới.
  * `#!/bin/bash` có nghĩa là: "Hãy sử dụng chương trình Bash shell (nằm ở đường dẫn `/bin/bash`) để thực thi tệp này."
  * Nếu bạn muốn dùng một shell khác, bạn có thể chỉ định nó, ví dụ: `#!/bin/sh` (cho Bourne shell) hoặc `#!/bin/zsh` (cho Z shell). Ngay cả các ngôn ngữ kịch bản khác cũng dùng nó, ví dụ: `#!/usr/bin/env python3`. 
### c. Cách chạy
#### Cách 1: `bash script.sh`
* **Cách thức:** Bạn gọi trực tiếp trình thông dịch `bash` và truyền tên tệp (`script.sh`) làm đối số (input) cho nó.
* **Quyền:** Tệp **không cần** quyền thực thi (`+x`) vì `bash` vốn đã có quyền thực thi, nên máy chỉ cần quyền đọc (read) tệp là đủ.
* **Shebang:** Dòng shebang (`#!/bin/bash`) **bị bỏ qua**, vì bạn đã chỉ định rõ ràng là dùng `bash` để chạy nó.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo '#!/bin/bash' > cat-script.sh
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo 'cat ~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/README.md | head' > cat-script.sh
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ bash cat-script.sh 
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
```
#### Cách 2: `chmod +x script.sh` (và `./script.sh`)
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ./cat-script.sh
bash: ./cat-script.sh: Permission denied
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l
total 8
-rw-rw-r-- 1 ngtukien ngtukien   99 Oct 31 19:49 cat-script.sh
drwxrwxr-x 4 ngtukien ngtukien 4096 Oct 30 10:11 kiennt_b23dccn465_training_gd1
```
* Vì bạn đang yêu cầu hệ điều hành (Kernel) chạy tệp `cat-script.sh` như 1 chương trình độc lập. 
* Nhưng vì lý do bảo mật, Kelnel sẽ kiểm tra **quyền thực thi (execute permission)** của tệp trước. 
* Nếu tệp không có quyền này, bạn sẽ nhận được lỗi `Permission denied`. 
* Nếu có, Kernel sẽ đọc dòng đầu tiền (`#!/bin/bash`) để biết phải dùng trình thông dịch nào.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ls -l
total 8
-rwxrwxr-x 1 ngtukien ngtukien   99 Oct 31 19:49 cat-script.sh
drwxrwxr-x 4 ngtukien ngtukien 4096 Oct 30 10:11 kiennt_b23dccn465_training_gd1
```
* **`chmod +x script.sh`**: Lệnh này thay đổi quyền của tệp, thêm (add) quyền "thực thi" (e**x**ecute) cho nó.
* **`./script.sh`**: Sau khi có quyền, bạn thực thi tệp.
    * Dấu `./` là cần thiết để chỉ cho shell biết rằng tệp bạn muốn chạy nằm "trong thư mục hiện tại" (.).
    * **Cách thức:** Khi bạn chạy tệp theo cách này, hệ điều hành sẽ tự động đọc dòng **shebang** (`#!/bin/bash`) ở đầu tệp để biết *phải dùng trình thông dịch nào* để chạy nó.
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ ./cat-script.sh
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
    ```
## 2. Biến, vòng lặp và điều kiện
###  **a. Biến (Variables)**
Biến dùng để **lưu giá trị** tạm thời (chuỗi, số, đường dẫn, v.v).
```bash
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ name=Kien
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ age=20
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo "Ten:$name, Tuoi:$age"
Ten:Kien, Tuoi:20
```
* Không có dấu cách quanh `=`
* Dùng `$` để truy cập giá trị biến (`$name`)
### **b. Biến môi trường (Environment Variables)**
Là các biến **có sẵn trong hệ thống**, dùng để mô tả thông tin người dùng, thư mục, hệ điều hành,…

| Biến     | Ý nghĩa                                  |
| -------- | ---------------------------------------- |
| `$USER`  | Tên người dùng hiện tại                  |
| `$HOME`  | Thư mục chính của người dùng             |
| `$PATH`  | Danh sách thư mục chứa các lệnh thực thi |
| `$PWD`   | Thư mục hiện tại                         |
| `$SHELL` | Trình shell đang dùng (bash, zsh, sh, …) |

📘 Ví dụ:
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo "Người dùng : $USER"
Người dùng : ngtukien
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo "Thư mục chính : $HOME"
Thư mục chính : /home/ngtukien
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ echo "Thư mục hiện tại : $PWD"
Thư mục hiện tại : /home/ngtukien/Documents/TYP/typ-training-2025
```
### **d. Vòng lặp (Loops)**
* `for` loop: Dùng để lặp qua danh sách hoặc phạm vi số.
    * **Ví dụ 1:** Lặp qua danh sách:
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025$ for name in Phuong Hue Thang Toan Kien
    > do
    > echo "Xin chào $name"
    > done
    Xin chào Phuong
    Xin chào Hue
    Xin chào Thang
    Xin chào Toan
    Xin chào Kien
    ```
    * **Ví dụ 2:** Lặp qua số:
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ for i in {1..5}
    > do
    >   echo "Lần thứ $i"
    > done
    Lần thứ 1
    Lần thứ 2
    Lần thứ 3
    Lần thứ 4
    Lần thứ 5
    ```
* `while` loop: Lặp khi điều kiện **đúng (true)**.
  * **Ví dụ:**
    ```shell
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ count=1
    ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ while [ $count -le 5 ]
    > do
    >   echo "Đếm: $count"
    >   count=$((count + 1))
    > done
    Đếm: 1
    Đếm: 2
    Đếm: 3
    Đếm: 4
    Đếm: 5
    ```
### **c. Cấu trúc điều kiện (`if`)**
Dùng để kiểm tra điều kiện logic.
**Ví dụ 1: Kiểm tra số**
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ x=10
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ if [ $x -gt 5 ]; then
>   echo "x lớn hơn 5"
> else
>   echo "x không lớn hơn 5"
> fi
x lớn hơn 5
```
**Ví dụ 2: Kiểm tra file có tồi tại trong thư mục hiện tại**
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ if [ -f "test.txt" ]; then
>   echo "File tồn tại"
> else
>   echo "Không tìm thấy file"
> fi
Không tìm thấy file
```
**Ví dụ 3: Kiểm tra với lệnh (Command)**
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ if ls Image/ > /dev/null 2>&1 ; then  echo "Có tồn tại file"; else echo "Thư mục rỗng"; fi
Có tồn tại file
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ if ls Empty/ > /dev/null 2>&1 ; then  echo "Có tồn tại file"; else echo "Thư mục rỗng"; fi
Có tồn tại file
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls Empty/
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ 
```
* Ở đây, vì cả 2 đều có thể thực thi, `bash` sẽ coi đó là `true` nên `if` sẽ thực thi phần lệnh sau `then`.
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ ls Error/
ls: cannot access 'Error/': No such file or directory
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ if ls Error/ > /dev/null 2>&1 ; then  echo "Có tồn tại file"; else echo "Thư mục rỗng"; fi
Thư mục rỗng
```
* Còn nếu lệnh không thể thực thi (lỗi), `bash` sẽ hiểu đó là `false` và sẽ chạy lệnh sau `else`.
## 3. Tự động hóa tác vụ
### a.  `cron` và `crontab`
* **`cron`**: Là một "daemon" (một dịch vụ chạy nền) của hệ thống. Công việc duy nhất của nó là kiểm tra tệp `crontab` mỗi phút để xem có tác vụ nào cần chạy ngay bây" "giờ không.
* **`crontab`**: Viết tắt của "cron table", đây là một tệp văn bản đơn giản. Mỗi dòng trong tệp này định nghĩa một tác vụ (một "cron job"), bao gồm lịch chạy và lệnh (script) sẽ được chạy.
### b. `crontab -e`
Đây là lệnh quan trọng nhất. `e` là viết tắt của "edit" (chỉnh sửa).
Khi bạn gõ `crontab -e`, hệ thống sẽ mở tệp crontab của riêng bạn bằng trình soạn thảo văn bản mặc định (thường là `nano` hoặc `vim`). Sau khi bạn lưu và thoát, `cron` sẽ tự động đọc tệp mới này và áp dụng lịch trình của bạn.
### Cú pháp lên lịch (Crontab Syntax)
Đây là phần cốt lõi. Mỗi dòng trong `crontab` có 6 cột, 5 cột đầu tiên là thời gian, cột cuối cùng là lệnh cần chạy:
```
┌───────────── phút (0 - 59)
│ ┌───────────── giờ (0 - 23)
│ │ ┌───────────── ngày trong tháng (1 - 31)
│ │ │ ┌───────────── tháng (1 - 12)
│ │ │ │ ┌───────────── ngày trong tuần (0 - 6) (Chủ Nhật=0 hoặc 7)
│ │ │ │ │
* * * * * /đường/dẫn/tuyệt/đối/đến/script.sh
```
**Dấu `*` (sao) có nghĩa là "mỗi"**. Ví dụ, `*` ở cột "giờ" có nghĩa là "mỗi giờ".
### Ví dụ cách lên lịch chạy script
Giả sử bạn có một script tên là `script.sh` nằm ở `ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/script.sh$`.
**Rất quan trọng:**
1.  Script của bạn **phải** có quyền thực thi (`chmod +x ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/script.sh`).
2.  Bạn **phải** sử dụng đường dẫn tuyệt đối (đầy đủ), vì `cron` không biết thư mục hiện tại của bạn là gì.
-----
**Ví dụ 1: Chạy script mỗi phút (để kiểm tra)**
(Cẩn thận, chỉ dùng để test)
```shell
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ cat script.sh 
#!/bin/bash
TIMESTAMP=$(date "+%Y-%m-%d_%H-%M-%S")
echo "CRON RUN: $TIMESTAMP" >> /home/ngtukien/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/log.txt
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ crontab -e
crontab: installing new crontab
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ crontab -l
# Edit this file to introduce tasks to be run by cron.
* * * * * /home/ngtukien/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux/script.sh 
# Each task to run has to be defined through a single line
# indicating with different fields when the task will be run
# and what command to run for the task
# 
# To define the time you can provide concrete values for
# minute (m), hour (h), day of month (dom), month (mon),
# and day of week (dow) or use '*' in these fields (for 'any').
# 
# Notice that tasks will be started based on the cron's system
# daemon's notion of time and timezones.
# 
# Output of the crontab jobs (including errors) is sent through
# email to the user the crontab file belongs to (unless redirected).
# 
# For example, you can run a backup of all your user accounts
# at 5 a.m every week with:
# 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
# 
# For more information see the manual pages of crontab(5) and cron(8)
# 
# m h  dom mon dow   command
ngtukien@NgTuKien:~/Documents/TYP/typ-training-2025/kiennt_b23dccn465_training_gd1/Tuan_2_Linux$ tail -5 log.txt 
CRON RUN: 2025-10-31_21-16-01
CRON RUN: 2025-10-31_21-17-01
CRON RUN: 2025-10-31_21-18-01
CRON RUN: 2025-10-31_21-19-01
CRON RUN: 2025-10-31_21-20-01
```
**Ví dụ 2: Chạy script vào lúc 2:30 sáng mỗi ngày**
```bash
30 2 * * * /home/ngtukien/scripts/backup.sh
```
**Ví dụ 3: Chạy script vào 5 giờ chiều các ngày Thứ Hai (1) và Thứ Sáu (5)**
```bash
0 17 * * 1,5 /home/ngtukien/scripts/backup.sh
```
*(Lưu ý: 17 là 5 giờ chiều theo đồng hồ 24 giờ)*
**Ví dụ 4: Chạy script 15 phút một lần (vào các phút 0, 15, 30, 45 của mỗi giờ)**
```bash
*/15 * * * * /home/ngtukien/scripts/backup.sh
```
