## 2. Port and protocols

![Port là gì và ứng dụng của port trong hệ thống mạng | Viettelco](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/List-port.jpg)

### 3. Install and Lab Setup

### 4. Nmap Scan and Techniques

![image-20210427114248692](/image-20210427114248692.png)

### 5. Nmap Target Selection and Techniques

Nmap 7.60 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <inputfilename>: Input from list of hosts/networks
  -iR <num hosts>: Choose random targets
  --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
  --excludefile <exclude_file>: Exclude list from file
HOST DISCOVERY:
  -sL: List Scan - simply list targets to scan
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
  -PS/PA/PU/PY[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports
  -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
  -PO[protocol list]: IP Protocol Ping
  -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
  --dns-servers <serv1[,serv2],...>: Specify custom DNS servers
  --system-dns: Use OS's DNS resolver
  --traceroute: Trace hop path to each host
SCAN TECHNIQUES:
  -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
  -sU: UDP Scan
  -sN/sF/sX: TCP Null, FIN, and Xmas scans
  --scanflags <flags>: Customize TCP scan flags
  -sI <zombie host[:probeport]>: Idle scan
  -sY/sZ: SCTP INIT/COOKIE-ECHO scans
  -sO: IP protocol scan
  -b <FTP relay host>: FTP bounce scan
PORT SPECIFICATION AND SCAN ORDER:
  -p <port ranges>: Only scan specified ports
    Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
  --exclude-ports <port ranges>: Exclude the specified ports from scanning
  -F: Fast mode - Scan fewer ports than the default scan
  -r: Scan ports consecutively - don't randomize
  --top-ports <number>: Scan <number> most common ports
  --port-ratio <ratio>: Scan ports more common than <ratio>
SERVICE/VERSION DETECTION:
  -sV: Probe open ports to determine service/version info
  --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
  --version-light: Limit to most likely probes (intensity 2)
  --version-all: Try every single probe (intensity 9)
  --version-trace: Show detailed version scan activity (for debugging)
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script=<Lua scripts>: <Lua scripts> is a comma separated list of
           directories, script-files or script-categories
  --script-args=<n1=v1,[n2=v2,...]>: provide arguments to scripts
  --script-args-file=filename: provide NSE script args in a file
  --script-trace: Show all data sent and received
  --script-updatedb: Update the script database.
  --script-help=<Lua scripts>: Show help about scripts.
           <Lua scripts> is a comma-separated list of script-files or
           script-categories.
OS DETECTION:
  -O: Enable OS detection
  --osscan-limit: Limit OS detection to promising targets
  --osscan-guess: Guess OS more aggressively
TIMING AND PERFORMANCE:
  Options which take <time> are in seconds, or append 'ms' (milliseconds),
  's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m).
  -T<0-5>: Set timing template (higher is faster)
  --min-hostgroup/max-hostgroup <size>: Parallel host scan group sizes
  --min-parallelism/max-parallelism <numprobes>: Probe parallelization
  --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>: Specifies
      probe round trip time.
  --max-retries <tries>: Caps number of port scan probe retransmissions.
  --host-timeout <time>: Give up on target after this long
  --scan-delay/--max-scan-delay <time>: Adjust delay between probes
  --min-rate <number>: Send packets no slower than <number> per second
  --max-rate <number>: Send packets no faster than <number> per second
FIREWALL/IDS EVASION AND SPOOFING:
  -f; --mtu <val>: fragment packets (optionally w/given MTU)
  -D <decoy1,decoy2[,ME],...>: Cloak a scan with decoys
  -S <IP_Address>: Spoof source address
  -e <iface>: Use specified interface
  -g/--source-port <portnum>: Use given port number
  --proxies <url1,[url2],...>: Relay connections through HTTP/SOCKS4 proxies
  --data <hex string>: Append a custom payload to sent packets
  --data-string <string>: Append a custom ASCII string to sent packets
  --data-length <num>: Append random data to sent packets
  --ip-options <options>: Send packets with specified ip options
  --ttl <val>: Set IP time-to-live field
  --spoof-mac <mac address/prefix/vendor name>: Spoof your MAC address
  --badsum: Send packets with a bogus TCP/UDP/SCTP checksum
OUTPUT:
  -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3,
     and Grepable format, respectively, to the given filename.
  -oA <basename>: Output in the three major formats at once
  -v: Increase verbosity level (use -vv or more for greater effect)
  -d: Increase debugging level (use -dd or more for greater effect)
  --reason: Display the reason a port is in a particular state
  --open: Only show open (or possibly open) ports
  --packet-trace: Show all packets sent and received
  --iflist: Print host interfaces and routes (for debugging)
  --append-output: Append to rather than clobber specified output files
  --resume <filename>: Resume an aborted scan
  --stylesheet <path/URL>: XSL stylesheet to transform XML output to HTML
  --webxml: Reference stylesheet from Nmap.Org for more portable XML
  --no-stylesheet: Prevent associating of XSL stylesheet w/XML output
MISC:
  -6: Enable IPv6 scanning
  -A: Enable OS detection, version detection, script scanning, and traceroute
  --datadir <dirname>: Specify custom Nmap data file location
  --send-eth/--send-ip: Send using raw ethernet frames or IP packets
  --privileged: Assume that the user is fully privileged
  --unprivileged: Assume the user lacks raw socket privileges
  -V: Print version number
  -h: Print this help summary page.
EXAMPLES:
  nmap -v -A scanme.nmap.org
  nmap -v -sn 192.168.0.0/16 10.0.0.0/8
  nmap -v -iR 10000 -Pn -p 80
SEE THE MAN PAGE (https://nmap.org/book/man.html) FOR MORE OPTIONS AND EXAMPLES



Nmap 7.60 (https://nmap.org)
Cách sử dụng: nmap [(Các) loại quét] [Tùy chọn] {target đặc tả}
ĐẶC ĐIỂM MỤC TIÊU:
  Có thể chuyển tên máy chủ, địa chỉ IP, mạng, v.v.
  Ví dụ: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <inputfilename>: Đầu vào từ danh sách máy chủ / mạng
  -iR <num hosts>: Chọn mục tiêu ngẫu nhiên
  --exclude <host1 [, host2] [, host3], ...>: Loại trừ các máy chủ / mạng
  --excludefile <exclude_file>: Loại trừ danh sách khỏi tệp
KHÁM PHÁ HOST:
  -sL: Quét danh sách - chỉ cần liệt kê các mục tiêu để quét
  -sn: Ping Scan - tắt tính năng quét cổng
  -Pn: Coi tất cả các máy chủ là trực tuyến - bỏ qua việc khám phá máy chủ
  -PS / PA / PU / PY [danh sách cổng]: Khám phá TCP SYN / ACK, UDP hoặc SCTP tới các cổng nhất định
  -PE / PP / PM: ICMP echo, timestamp và netmask request thăm dò
  -PO [danh sách giao thức]: Giao thức IP Ping
  -n / -R: Không bao giờ phân giải DNS / Luôn phân giải [mặc định: đôi khi]
  --dns-server <serv1 [, serv2], ...>: Chỉ định máy chủ DNS tùy chỉnh
  --system-dns: Sử dụng trình phân giải DNS của hệ điều hành
  --traceroute: Theo dõi đường dẫn hop đến từng máy chủ
KỸ THUẬT QUÉT:
  -sS / sT / sA / sW / sM: quét TCP SYN / Connect () / ACK / Window / Maimon
  -sU: Quét UDP
  -sN / sF / sX: quét TCP Null, FIN và Xmas
  --scanflags <flags>: Tùy chỉnh cờ quét TCP
  -sI <zombie host [: probeport]>: Quét không hoạt động
  -sY / sZ: Quét SCTP INIT / COOKIE-ECHO
  -sO: quét giao thức IP
  -b <FTP relay host>: FTP bounce scan
ĐẶC ĐIỂM CỔNG VÀ TRÌNH TỰ QUÉT:
  -p <phạm vi cổng>: Chỉ quét các cổng được chỉ định
    Ví dụ: -p22; -p1-65535; -p U: 53,111,137, T: 21-25,80,139,8080, S: 9
  --exclude-port <port range>: Loại trừ các cổng được chỉ định khỏi quá trình quét
  -F: Chế độ nhanh - Quét ít cổng hơn so với quét mặc định
  -r: Quét các cổng liên tục - không ngẫu nhiên
  --top-port <number>: Quét <number> các cổng phổ biến nhất
  --port-ratio <ratio>: Quét các cổng phổ biến hơn <ratio>
DỊCH VỤ / PHIÊN BẢN PHÁT HIỆN:
  -sV: Thăm dò các cổng đang mở để xác định thông tin dịch vụ / phiên bản
  --version-Cường độ <level>: Đặt từ 0 (sáng) đến 9 (thử tất cả các đầu dò)
  - ánh sáng ngược: Giới hạn đối với các đầu dò có khả năng xảy ra nhất (cường độ 2)
    --version-all: Thử mọi đầu dò (cường độ 9)
    --version-trace: Hiển thị hoạt động quét phiên bản chi tiết (để gỡ lỗi)
QUÉT KHỎI:
    -sC: tương đương với --script = default
    --script = <Lua scripts>: <Lua scripts> là danh sách được phân tách bằng dấu phẩy của
           thư mục, tập tin kịch bản hoặc danh mục tập lệnh
    --script-args = <n1 = v1, [n2 = v2, ...]>: cung cấp đối số cho tập lệnh
    --script-args-file = filename: cung cấp args tập lệnh NSE trong một tệp
    --script-trace: Hiển thị tất cả dữ liệu được gửi và nhận
    --script-updatedb: Cập nhật cơ sở dữ liệu tập lệnh.
    --script-help = <Lua scripts>: Hiển thị trợ giúp về tập lệnh.
           <Lua scripts> là danh sách được phân tách bằng dấu phẩy gồm các tệp script hoặc
           kịch bản-danh mục.
PHÁT HIỆN HỆ ĐIỀU HÀNH:
    -O: Bật phát hiện hệ điều hành
    --osscan-limit: Giới hạn phát hiện hệ điều hành đối với các mục tiêu hứa hẹn
    --osscan-đoán: Đoán hệ điều hành mạnh mẽ hơn
THỜI GIAN VÀ HIỆU SUẤT:
    Các tùy chọn mất <thời gian> tính bằng giây hoặc thêm 'mili giây' (mili giây),
    's' (giây), 'm' (phút) hoặc 'h' (giờ) thành giá trị (ví dụ: 30m).
    -T <0-5>: Đặt mẫu thời gian (cao hơn thì nhanh hơn)
    --min-hostgroup / max-hostgroup <size>: Kích thước nhóm quét máy chủ song song
    --min -llelism / max -llelism <numprobes>: Kiểm tra song song
    --min-rtt-timeout / max-rtt-timeout / Initial-rtt-timeout <time>: Chỉ định
      thăm dò thời gian khứ hồi.
    --max-retries <tries>: Giới hạn số lần truyền lại đầu dò quét cổng.
    --host-timeout <time>: Từ bỏ mục tiêu sau một thời gian dài
    --scan-delay / - max-scan-delay <time>: Điều chỉnh độ trễ giữa các đầu dò
    --min-rate <number>: Gửi gói không chậm hơn <number> mỗi giây
    --max-rate <number>: Gửi gói không nhanh hơn <number> mỗi giây
ĐÁNH GIÁ FIREWALL / IDS VÀ SPOOFING:
    -f; --mtu <val>: gói phân mảnh (tùy chọn có MTU đã cho)
    -D <decoy1, decoy2 [, ME], ...>: Che dấu vết quét bằng mồi nhử
    -S <IP_Address>: Địa chỉ nguồn giả mạo
    -e <iface>: Sử dụng giao diện được chỉ định
    -g / - source-port <portnum>: Sử dụng số cổng đã cho
    --proxies <url1, [url2], ...>: Chuyển tiếp kết nối thông qua proxy HTTP / SOCKS4
    --data <hex string>: Nối trọng tải tùy chỉnh vào các gói đã gửi
    --data-string <string>: Nối một chuỗi ASCII tùy chỉnh vào các gói đã gửi
    --data-length <num>: Nối dữ liệu ngẫu nhiên vào các gói đã gửi
    --ip-options <options>: Gửi các gói với các tùy chọn ip được chỉ định
    --ttl <val>: Đặt trường thời gian tồn tại IP
    --spoof-mac <địa chỉ mac / tiền tố / tên nhà cung cấp>: Giả mạo địa chỉ MAC của bạn
    --badsum: Gửi các gói với tổng kiểm tra TCP / UDP / SCTP không có thật
ĐẦU RA:
    -oN / -oX / -oS / -oG <file>: Quét đầu ra ở dạng bình thường, XML, s | <rIpt kIddi3,
     và định dạng Grepable, tương ứng với tên tệp đã cho.
    -oA <basename>: Đầu ra ở ba định dạng chính cùng một lúc
    -v: Tăng mức độ chi tiết (sử dụng -vv trở lên để có hiệu quả cao hơn)
    -d: Tăng mức gỡ lỗi (sử dụng -dd trở lên để có hiệu quả cao hơn)
    --reason: Hiển thị lý do một cổng ở trạng thái cụ thể
    --open: Chỉ hiển thị các cổng đang mở (hoặc có thể đang mở)
    --packet-trace: Hiển thị tất cả các gói được gửi và nhận
    --iflist: In giao diện máy chủ và các tuyến (để gỡ lỗi)
  - ứng dụng

### 6. Nmap Port Scan and Techniques

#### Name Scan 

![image-20210427120910170](/image-20210427120910170.png)

#### Port Scan

![image-20210427121049091](/image-20210427121049091.png)

#### Summary

![image-20210427121159987](/image-20210427121159987.png)

### 7. Nmap Service Detection

### 8. Nmap OS Detection

sudo nmap 192.168.10.12 -O -v -Pn

-Pn: Co kha nang vuot qua tuong lua

### 9. Nmap Output Formats

Nomal: nmap scanme.nmap.org -p- -v -oN normaloutput.txt

-p-: 

```
-p- to scan
    ports from 1 through 65535.
```

### 10. Nmap Script scan

help: nmap 127.0.0.1 --script-help=http-methods

![image-20210427151755126](/image-20210427151755126.png)

### 11. Nmap Script Attacks Categories

![image-20210427152036495](/image-20210427152036495.png)

![image-20210427152140270](/image-20210427152140270.png)



![image-20210427152216303](/image-20210427152216303.png)



![image-20210427152409439](/
image-20210427152409439.png)





![image-20210427152610639](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427152610639.png)





![image-20210427152645076](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427152645076.png)



![image-20210427152733810](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427152733810.png)



![image-20210427152802014](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427152802014.png)

![image-20210427152837998](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427152837998.png)



### 12. Nmap for Reconnaisance

![image-20210427153058426](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153058426.png)



![image-20210427153157833](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153157833.png)



![image-20210427153310712](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153310712.png)

![image-20210427153325527](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153325527.png)

![image-20210427153402356](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153402356.png)



![image-20210427153423964](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153423964.png)![image-20210427153523790](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153523790.png)



![image-20210427153549187](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153549187.png)

![image-20210427153912546](/home/quangg/Downloads/khóa hoc/NSTH-Ethical.Hacking.Network.Security.Pentesting.Nmap/image-20210427153912546.png)	

### 13. Mail Exploitation
