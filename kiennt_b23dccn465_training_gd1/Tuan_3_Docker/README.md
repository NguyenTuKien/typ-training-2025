# Phần 1: Tổng quan về ảo hóa

---
## 1. Khái niệm Ảo hoá (Virtualization)
* **Ảo hoá (Virtualization)** là **công nghệ cho phép tạo ra nhiều môi trường hoặc tài nguyên “ảo”** (như máy tính, máy chủ, bộ nhớ, hay mạng) trên cùng **một phần cứng vật lý duy nhất**.
Nói cách khác, ảo hoá giúp **một máy vật lý hoạt động như nhiều máy độc lập**.
  * Ví dụ: Một máy chủ vật lý có thể “ảo hoá” thành nhiều **máy ảo (Virtual Machines – VM)**, mỗi máy ảo có thể chạy **hệ điều hành và ứng dụng riêng biệt**.
* **Lớp ảo hóa (Hypervisor)** là phần mềm trung gian **giữa phần cứng và các máy ảo**, giúp chia sẻ tài nguyên (CPU, RAM, ổ cứng,...) cho từng máy ảo.
  * Ví dụ: VMware, VirtualBox, KVM, Hyper-V.
* **Máy ảo (Virtual Machine – VM)** là **một hệ thống máy tính ảo**, mô phỏng phần cứng thật, có thể cài hệ điều hành và ứng dụng như một máy thật.

![img.png](Image/hypervisor.png)
### **Mục đích của Ảo hoá**
* **Tối ưu sử dụng tài nguyên phần cứng :** Giúp nhiều hệ thống chạy trên cùng một máy vật lý, tránh lãng phí tài nguyên.
* **Giảm chi phí đầu tư và vận hành :** Không cần mua nhiều máy chủ vật lý, tiết kiệm điện năng, không gian, và chi phí bảo trì.
* **Tăng khả năng linh hoạt và mở rộng :** Dễ dàng tạo, sao chép, di chuyển, hoặc khôi phục máy ảo khi cần.
* **Tăng tính an toàn và cách ly :** Mỗi máy ảo hoạt động độc lập; lỗi hoặc tấn công trong một VM không ảnh hưởng đến VM khác.
* **Thuận tiện cho phát triển, kiểm thử và đào tạo :** Dễ tạo môi trường test, thử nghiệm hệ điều hành mới, hoặc học cấu hình server mà không sợ hỏng máy thật.

---
## 2. Các loại ảo hóa và công nghệ ảo hóa thông dụng
### a. Ảo hóa hệ thống lưu trữ (Storage Virtualization)
* **Ảo hóa lưu trữ** là quá trình **tập hợp (gộp)** nhiều thiết bị lưu trữ vật lý (như HDD, SSD, SAN, NAS...) thành **một không gian lưu trữ ảo thống nhất**.
* Người dùng và ứng dụng chỉ thấy **một khối lưu trữ duy nhất**, không cần biết dữ liệu nằm ở thiết bị nào.
* **Mục đích** : Tăng hiệu suất, dễ quản lý, phân bổ dung lượng linh hoạt và đảm bảo tính sẵn sàng cao (HA – High Availability).

| Loại ảo hóa                             | Mô tả ngắn gọn                                                              | Cách hoạt động                                                                                                                 | Một số công nghệ/giải pháp tiêu biểu                                      |
| --------------------------------------- |-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------| ------------------------------------------------------------------------- |
| **Host-based virtualization**           | Ngăn cách giữa lớp ảo háo và ổ đĩa vật lý là **drive điều khiển** các ổ đĩa.| Phần mềm ảo hóa tổng hợp các thiết bị lưu trữ vật lý và và sẽ truy xuất tài nguyên thông qua sự điều khiển của lớp Driver này. | Windows Storage Spaces, Linux LVM, Veritas Volume Manager                 |
| **Storage-device based virtualization** | Phần mềm ảo hóa nằm **trực tiếp trong thiết bị lưu trữ** (như SAN/NAS).     | Bộ điều khiển (controller) trong thiết bị lưu trữ tự động gộp và phân vùng tài nguyên, cung cấp cho nhiều máy chủ.             | EMC VNX, NetApp ONTAP, IBM DS8000, Dell PowerVault                        |
| **Network-based virtualization**        | Ảo hóa ở **lớp mạng lưu trữ (SAN/NAS switch)**.                             | Thiết bị hoặc phần mềm trung gian gom dữ liệu từ nhiều nguồn, phân phối động đến các máy chủ.                                  | IBM SAN Volume Controller (SVC), Brocade, Cisco MDS, DataCore SANsymphony |

![img.png](Image/storage_virtualization.png)
### b. Ảo hóa hệ thống mạng (Network Virtualization)
* Ảo hóa mạng là kỹ thuật tạo ra **nhiều mạng ảo độc lập** hoạt động trên **một hạ tầng vật lý duy nhất**.
→ Giúp chia hoặc gộp các thiết bị mạng (switch, router, firewall...) để sử dụng linh hoạt và hiệu quả hơn.
* **Phân loại**

| Loại ảo hóa  | Mô tả ngắn                                            | Ví dụ                       |
| ------------ | ----------------------------------------------------- | --------------------------- |
| **Internal** | Tạo nhiều mạng ảo bên trong 1 máy chủ vật lý.         | VMware vSwitch, Hyper-V     |
| **External** | Gom nhiều thiết bị vật lý thành 1 mạng ảo thống nhất. | VLAN, VXLAN, SDN, Cisco ACI |
![img.png](Image/network_virtualization.png)
### c. Ảo hóa hệ thống ứng dụng (Application Virtualization)
* Là công nghệ cho phép **tách rời ứng dụng khỏi hệ điều hành**, giúp **phân phối và chạy ứng dụng linh hoạt** hơn, mà **không cần cài đặt trực tiếp** lên máy người dùng.
* **Ưu điểm:**
  * Giúp dễ dàng cập nhật, quản lý và khắc phục lỗi ứng dụng.
  * Người dùng có thể trải nghiệm ứng dụng như bình thường.
  * Giảm xung đột giữa các ứng dụng hoặc giữa ứng dụng và hệ điều hành.
* **Một số nền tảng phổ biến:** Citrix XenApp, Microsoft Application Virtualization, VMware ThinApp.
#### **Hai công nghệ chính:**
* **Application Streaming**
    * Ứng dụng được chia thành các đoạn và **truyền dần đến người dùng khi cần** (không cần tải toàn bộ).
    * Dữ liệu truyền qua HTTP, CIFS hoặc RTSP.
* **Desktop Virtualization / VDI (Virtual Desktop Infrastructure)**
    * Ứng dụng được cài đặt và chạy trên **máy ảo (virtual desktop)**.
    * Hệ thống quản lý sẽ tạo và cung cấp desktop ảo cho người dùng.
### d. Ảo hóa hệ thống máy chủ (Server Virtualization)
* Là công nghệ cho phép **chạy nhiều máy ảo (VM)** trên **một máy chủ vật lý**, giúp:
* **Mục đích :** 
  * Tăng **tính linh động**, dễ thiết lập và quản lý.
  * **Tiết kiệm tài nguyên**, chia sẻ tốt hơn giữa các ứng dụng.
  * **Tăng hiệu suất** và khả năng tận dụng phần cứng.
#### **Hai mô hình ảo hóa máy chủ chính**

| Loại ảo hóa                                      | Đặc điểm chính                                                                                                                                                                                                          | Ví dụ công nghệ                                                                       |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Host-based** (hay Hosted Hypervisor)           | - Hypervisor chạy **trên hệ điều hành chủ (host OS)**.<br> - Dễ cài đặt, thích hợp cho **môi trường cá nhân hoặc thử nghiệm**.<br> - Hiệu năng thấp hơn do phải thông qua hệ điều hành trung gian.                      | VMware Workstation, VMware Server, Microsoft Virtual Server                           |
| **Hypervisor-based** (hay Bare-metal Hypervisor) | - Hypervisor chạy **trực tiếp trên phần cứng** của máy chủ (không qua hệ điều hành).<br> - **Hiệu năng cao hơn**, thường dùng trong **doanh nghiệp và trung tâm dữ liệu**.<br> - Quản lý tài nguyên và VM hiệu quả hơn. | Oracle VM, VMware ESX/ESXi, Microsoft Hyper-V, Citrix XenServer, IBM Power Hypervisor |
### e. Các công nghệ ảo hóa đã từng dùng
#### **VMware – Ảo hóa máy chủ (Server Virtualization)**
* **Loại ảo hóa:** 🖥️ *Ảo hóa hệ thống máy chủ (Hypervisor-based hoặc Host-based)*
* **Công nghệ:** VMware Workstation, VMware ESXi
* **Nguyên lý:** Cho phép chạy **nhiều máy ảo** (mỗi VM có hệ điều hành riêng) **trên một máy thật**.
* **Mục đích sử dụng:**
    * Tạo môi trường test hoặc dev độc lập.
    * Cài đặt nhiều OS để thử nghiệm phần mềm.
* **Ví dụ:**
    * Cài VMware Workstation trên Windows → chạy Ubuntu VM bên trong.
#### **Docker – Ảo hóa cấp ứng dụng (Application / OS-level Virtualization)**
* **Loại ảo hóa:** 🧱 *Ảo hóa hệ điều hành (OS-level / Container-based Virtualization)*
* **Công nghệ:** Docker Engine, Kubernetes
* **Nguyên lý:**
    * Không tạo máy ảo riêng biệt.
    * Thay vào đó, **chia sẻ kernel** của hệ điều hành, tạo các **container cô lập** chạy ứng dụng riêng.
* **Mục đích sử dụng:**
    * Triển khai ứng dụng nhanh, nhẹ, tách biệt môi trường.
* **Ví dụ:**
    * Chạy Spring Boot trong container riêng, database trong container khác, tất cả cùng trên 1 máy.
#### **Cloud – Ảo hóa kết hợp nhiều lớp**
* **Loại ảo hóa:**
    * Ảo hóa máy chủ (**Server Virtualization**) – chạy nhiều VM cho khách hàng.
    * Ảo hóa lưu trữ (**Storage Virtualization**) – gom nhiều ổ đĩa vật lý thành một không gian lưu trữ ảo.
    * Ảo hóa mạng (**Network Virtualization**) – chia mạng thành các subnet, VLAN, VPN riêng biệt.
* **Công nghệ:**
    * AWS EC2, Cloudflare R2, S3.
* **Mục đích:**
    * Cung cấp **tài nguyên ảo hóa on-demand** (máy ảo, ổ đĩa, mạng ảo) cho người dùng hoặc doanh nghiệp.

---
## 3. Virtual Machine
* Virtual Machine (VM) là một máy tính ảo được tạo ra bằng phần mềm (hypervisor), mô phỏng đầy đủ phần cứng của một máy thật (Host machine). Trên đó, bạn có thể cài và chạy hệ điều hành, phần mềm như trên máy vật lý.
* Khi hypervisor tạo VM, nó ảo hóa gần như toàn bộ tài nguyên phần cứng, bao gồm:

  | Thành phần                             | Ý nghĩa / Mô tả                                                      |
  | -------------------------------------- | -------------------------------------------------------------------- |
  | **CPU (Processor)**                    | Chia sẻ CPU vật lý thành nhiều CPU ảo cho từng VM.                   |
  | **RAM (Memory)**                       | Mỗi VM có vùng bộ nhớ ảo riêng, tách biệt với host và các VM khác.   |
  | **Storage (Ổ đĩa)**                    | Mỗi VM có “ổ đĩa ảo” (VDI, VMDK, v.v.) nằm trên ổ thật của host.     |
  | **Network (Card mạng)**                | Mỗi VM có card mạng ảo (vNIC), có thể kết nối LAN, NAT, hoặc Bridge. |
  | **I/O Devices (chuột, bàn phím, USB)** | Được ảo hóa để chia sẻ hoặc tách biệt giữa VM và host.               |
### a. Ảo hóa được hỗ trợ bởi phần cứng (Hardware-assisted Virtualization)
* Là cơ chế mà CPU và phần cứng của máy tính cung cấp chức năng đặc biệt để hỗ trợ ảo hóa, giúp máy ảo (VM) chạy nhanh hơn và ổn định hơn thay vì chạy qua phần mềm (hypervisor) mô phỏng.
* Một số nền tảng ảo hóa được hỗ trợ bởi phần cứng :

| Nền tảng                      | Tận dụng hardware virtualization như thế nào                     |
| ----------------------------- | ---------------------------------------------------------------- |
| **VMware Workstation / ESXi** | Sử dụng VT-x để cho phép guest OS chạy trực tiếp trên CPU        |
| **VirtualBox**                | Có tùy chọn “Enable VT-x / AMD-V” để tăng tốc VM                 |
| **KVM (Linux)**               | Dựa hoàn toàn vào VT-x/AMD-V — nếu không có, không thể chạy được |

* Kiểm tra khả năng ảo hóa của máy : `egrep -wo 'vmx|svm' /proc/cpuinfo`
  * `vmx` = Intel VT-x 
  * `svm` = AMD-V
  * Nếu không thấy, hãy vào BIOS / UEFI → bật “Intel Virtualization Technology” hoặc “SVM Mode”.
### b. Ảo hóa bán phần (Paravirtualization)
* Là hình thức ảo hóa trong đó hệ điều hành khách (Guest OS) biết rằng nó đang chạy trong môi trường ảo hóa, và hợp tác với hypervisor để thực hiện các tác vụ đặc quyền (privileged operations).
* Ví dụ: Khi máy áo cần ghi vào ổ cứng sector 1000.
  * Ảo hóa toàn phần (Full-virtualization) : Hypervisor sẽ giả lập toàn bộ ổ cứng, máy ảo sẽ nghĩ nó đang ghi trực tiếp vào ổ cứng thật. Khi máy ảo gửi lệnh "ghi sector 1000", hypervisor phải bắt (trap) lệnh đó lại, dịch nó, rồi mới thực thi trên phần cứng thật.
  * Ảo hóa bán phần (Paravirtualization) : VM sẽ gọi trực tiếp API của hypervisor (gọi là `hypercall`) để ghi vào sector 1000 trên ổ cứng thật, bỏ qua bước giả lập ổ cứng ảo.
* Ưu & nhược điểm :

| Ưu điểm                                                                 | Nhược điểm                                               |
| ----------------------------------------------------------------------- | -------------------------------------------------------- |
| 🚀 Hiệu năng cao hơn full virtualization (vì ít mô phỏng phần cứng hơn) | 🧩 Guest OS phải **được sửa đổi**, không thể dùng OS gốc |
| ⚡ Giao tiếp giữa guest và hypervisor nhanh hơn (qua hypercalls)         | Không phù hợp cho OS đóng (như Windows bản thương mại)   |
| 💾 Giảm overhead xử lý I/O, CPU, memory                                 | Cần hypervisor hỗ trợ kiểu này (Xen, KVM, v.v.)          |
### c. Vòng đời và quản lý VM
| Giai đoạn              | Mô tả                                                         |
| ---------------------- | ------------------------------------------------------------- |
| **Create (Tạo)**       | Hypervisor cấp tài nguyên và tạo đĩa ảo, CPU ảo, RAM cho VM.  |
| **Boot / Start**       | VM khởi động hệ điều hành của mình như máy thật.              |
| **Run**                | VM chạy ứng dụng, xử lý dữ liệu.                              |
| **Pause / Suspend**    | Tạm dừng trạng thái VM (giống sleep).                         |
| **Snapshot**           | Ghi lại trạng thái hiện tại (RAM, CPU, đĩa) để khôi phục sau. |
| **Resume**             | Khởi chạy lại VM từ snapshot hoặc trạng thái pause.           |
| **Shutdown / Destroy** | Dừng VM, giải phóng tài nguyên.                               |
* **Quản lý VM:**
  * Qua hypervisor GUI (VMware, VirtualBox, Hyper-V Manager).
  * Hoặc qua CLI / API (ví dụ: virsh, VBoxManage, vSphere API).
  * Có thể clone, migrate, backup hoặc scale dễ dàng.
  
---
# Phần 2: Container
## 1. Container là gì?
**Container** là công nghệ ảo hóa **ở mức hệ điều hành (OS-level virtualization)**.
Nó cho phép **nhiều ứng dụng** chạy độc lập trên cùng **một hệ điều hành** nhưng **tách biệt về môi trường** (file system, network, process,…).

Mỗi container chứa:
* Ứng dụng (App)
* Thư viện và dependencies cần thiết
* Nhưng **không có kernel riêng** (dùng chung kernel với host OS)

Công nghệ phổ biến: **Docker**, **Kubernetes**, **Podman**, **LXC**
### So sánh Container vs Virtual Machine

| Tiêu chí             | **Container**                                   | **Virtual Machine (VM)**                     |
| -------------------- | ----------------------------------------------- | -------------------------------------------- |
| **Mức độ ảo hóa**    | Ảo hóa **hệ điều hành**                         | Ảo hóa **phần cứng**                         |
| **Kernel**           | Dùng **chung kernel** của host                  | Mỗi VM có **kernel riêng**                   |
| **Tốc độ khởi động** | Rất nhanh (vài giây)                            | Chậm hơn (vài phút)                          |
| **Dung lượng**       | Nhẹ (MBs)                                       | Nặng (GBs)                                   |
| **Cách cô lập**      | Cô lập tiến trình (process-level isolation)     | Cô lập hoàn toàn (full OS isolation)         |
| **Hiệu năng**        | Gần như native (rất cao)                        | Giảm nhẹ do lớp ảo hóa                       |
| **Trường hợp dùng**  | Triển khai ứng dụng nhanh, CI/CD, microservices | Chạy nhiều OS khác nhau, môi trường phức tạp |
| **Công cụ phổ biến** | Docker, Kubernetes                              | VMware, VirtualBox, Hyper-V                  |
![img.png](Image/container.png)
