Lab01: Uvod v Kali Linux

Cilj
Cilj vaje je spoznati distribucijo Kali Linux, njeno uporabo v kibernetski varnosti
ter osnovno delo v grafičnem in ukaznem okolju.

Grafično okolje
Uporabljeno grafično okolje: Xfce

Pregled varnostnih orodij:
Nmap
ZenMap
tcpdump
htop
searchsploit

Raziskala sem nastavitve sistema in osnovni datotečni sistem (/home, /etc, /usr).

UKAZI IN REZUTATI:

Ukaz: whoami
Rezultat: kali

Ukaz: hostnamectl
Rezultat:  Static hostname: kali
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: b69758c0cad3481e967dcad827001d56
         Boot ID: 247c1157e5174ab78d3a3a246e61f6b8
  Virtualization: oracle
Operating System: Kali GNU/Linux Rolling          
          Kernel: Linux 6.16.8+kali-amd64
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Hardware Version: 1.2
Firmware Version: VirtualBox
   Firmware Date: Fri 2006-12-01
    Firmware Age: 19y 1month 2w 1d 

Ukaz: uname -a
Rezultat: Linux kali 6.16.8+kali-amd64 #1 SMP PREEMPT_DYNAMIC Kali 6.16.8-1kali1 (2025-09-24) x86_64 GNU/Linux

Ukaz: df -h
Rezultat: 
	Filesystem      Size  Used Avail Use% Mounted on
	udev            883M     0  883M   0% /dev
	tmpfs           198M  964K  197M   1% /run
	/dev/sda1        79G   16G   60G  21% /
	tmpfs           986M  4.0K  986M   1% /dev/shm
	none            1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
	tmpfs           986M  260K  986M   1% /tmp
	none            1.0M     0  1.0M   0% /run/credentials/getty@tty1.service
	tmpfs           198M  116K  197M   1% /run/user/1000
	
Ukaz: ip a
Rezultat:
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:63:b0:05 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute eth0
       valid_lft 82148sec preferred_lft 82148sec
    inet6 fe80::2839:e213:5340:a24d/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
     
Ukaz: wget https://gist.githubusercontent.com/EdwardRayl/3436572afde8ce9e3faf5b7b95356a49/raw/6b25895fce480713560829dec31ac8220ffe5272/gists.txt
Rezultat:
--2026-01-15 06:03:48--  https://gist.githubusercontent.com/EdwardRayl/3436572afde8ce9e3faf5b7b95356a49/raw/6b25895fce480713560829dec31ac8220ffe5272/gists.txt
Resolving gist.githubusercontent.com (gist.githubusercontent.com)... 185.199.108.133, 185.199.109.133, 185.199.110.133, ...
Connecting to gist.githubusercontent.com (gist.githubusercontent.com)|185.199.108.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9634 (9.4K) [text/plain]
Saving to: ‘gists.txt’

gists.txt           100%[================>]   9.41K  --.-KB/s    in 0.001s  

2026-01-15 06:03:48 (15.0 MB/s) - ‘gists.txt’ saved [9634/9634]

Ukaz: sudo apt install 7zip
Rezultat:
[sudo] password for kali: 
7zip is already the newest version (25.01+dfsg-4).
7zip set to manually installed.
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0
  
Ukaz: which nmap
Rezultat:
/usr/bin/nmap

Ukaz: which john
Rezultat:
/usr/sbin/john

Ukaz: ls -la   
Rezultat: 
total 976640
drwxr-xr-x  18 root root       4096 Dec  2 22:02 .
drwxr-xr-x  18 root root       4096 Dec  2 22:02 ..
lrwxrwxrwx   1 root root          7 Nov 10 04:50 bin -> usr/bin
drwxr-xr-x   3 root root       4096 Dec  2 22:03 boot
drwxr-xr-x  18 root root       3240 Jan 15 04:51 dev
drwxr-xr-x 180 root root      12288 Jan 15 04:52 etc
drwxr-xr-x   3 root root       4096 Dec  2 21:36 home
lrwxrwxrwx   1 root root         33 Dec  2 22:02 initrd.img -> boot/initrd.img-6.16.8+kali-amd64
lrwxrwxrwx   1 root root         33 Dec  2 22:02 initrd.img.old -> boot/initrd.img-6.16.8+kali-amd64
lrwxrwxrwx   1 root root          7 Nov 10 04:50 lib -> usr/lib
lrwxrwxrwx   1 root root          9 Dec  2 21:33 lib32 -> usr/lib32
lrwxrwxrwx   1 root root          9 Nov 10 04:50 lib64 -> usr/lib64
drwx------   2 root root      16384 Dec  2 22:01 lost+found
drwxr-xr-x   2 root root       4096 Dec  2 21:29 media
drwxr-xr-x   2 root root       4096 Dec  2 21:29 mnt
drwxr-xr-x   3 root root       4096 Dec  2 21:33 opt
dr-xr-xr-x 226 root root          0 Jan 15 04:51 proc
drwx------   4 root root       4096 Jan 15 04:51 root
drwxr-xr-x  36 root root        860 Jan 15 04:52 run
lrwxrwxrwx   1 root root          8 Nov 10 04:50 sbin -> usr/sbin
drwxr-xr-x   3 root root       4096 Dec  2 21:34 srv
-rw-------   1 root root 1000000000 Dec  2 22:02 swap
dr-xr-xr-x  13 root root          0 Jan 15 04:51 sys
drwxrwxrwt  12 root root        320 Jan 15 05:59 tmp
drwxr-xr-x  15 root root       4096 Dec  2 21:33 usr
drwxr-xr-x  12 root root       4096 Jan 15 04:51 var
lrwxrwxrwx   1 root root         30 Dec  2 22:02 vmlinuz -> boot/vmlinuz-6.16.8+kali-amd64
lrwxrwxrwx   1 root root         30 Dec  2 22:02 vmlinuz.old -> boot/vmlinuz-6.16.8+kali-amd64

Ukaz: sudo apt install htop -y
Installing:                     
  htop
                                                                             
Suggested packages:
  strace

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 976
  Download size: 171 kB
  Space needed: 434 kB / 63.1 GB available

Get:1 http://mirror.init7.net/kali kali-rolling/main amd64 htop amd64 3.4.1-5 [171 kB]
Fetched 171 kB in 0s (382 kB/s)
Selecting previously unselected package htop.
(Reading database ... 422160 files and directories currently installed.)
Preparing to unpack .../htop_3.4.1-5_amd64.deb ...
Unpacking htop (3.4.1-5) ...
Setting up htop (3.4.1-5) ...
Processing triggers for mailcap (3.75) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for desktop-file-utils (0.28-1) ...
Processing triggers for hicolor-icon-theme (0.18-2) ...
Processing triggers for man-db (2.13.1-1) ...


Ukaz: htop
Rezultat: 
Prikazan je pregled procesov, porabe CPU in RAM. q = izhod

Ukaz: sudo apt install traceroute -y
traceroute is already the newest version (1:2.1.6-1).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 976
                                                                             
Ukaz: traceroute google.com   
traceroute to google.com (142.251.39.14), 30 hops max, 60 byte packets
 1  10.0.2.2 (10.0.2.2)  0.276 ms  0.309 ms  0.252 ms
 1  10.0.2.2 (10.0.2.2)  6.060 ms  5.480 ms  5.042 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 ...
30  * * *

Ukaz: sudo apt install nload -y
Rezultat: 
Installing:                     
  nload
                                                                             
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 976
  Download size: 56.2 kB
  Space needed: 164 kB / 63.1 GB available

Get:1 http://http.kali.org/kali kali-rolling/main amd64 nload amd64 0.7.4-2+b1 [56.2 kB]
Fetched 56.2 kB in 0s (130 kB/s) 
Selecting previously unselected package nload.
(Reading database ... 422171 files and directories currently installed.)
Preparing to unpack .../nload_0.7.4-2+b1_amd64.deb ...
Unpacking nload (0.7.4-2+b1) ...
Setting up nload (0.7.4-2+b1) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for man-db (2.13.1-1) ...
                                                                             
ukaz: nload  
Rezultat: ...Graficni prikaz hitrosti podatkov.

Ukaz: strings /bin/ls | head
Rezultat: ASCII nizi iz binarne datoteke.
	!/lib64/ld-linux-x86-64.so.2
	_ITM_deregisterTMCloneTable
	__gmon_start__
	_ITM_registerTMCloneTable
	fgetfilecon_raw
	fgetfilecon
	freecon
	lgetfilecon
	lgetfilecon_raw
	_IO_stdin_used

Ukaz: sudo apt install speedtest-cli -y
Rezultat:
Installing:                     
  speedtest-cli
                                                                             
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 976
  Download size: 23.8 kB
  Space needed: 104 kB / 63.1 GB available

Get:1 http://kali.mirror.garr.it/kali kali-rolling/main amd64 speedtest-cli all 2.1.3-3 [23.8 kB]
Fetched 23.8 kB in 1s (43.9 kB/s)        
Selecting previously unselected package speedtest-cli.
(Reading database ... 422178 files and directories currently installed.)
Preparing to unpack .../speedtest-cli_2.1.3-3_all.deb ...
Unpacking speedtest-cli (2.1.3-3) ...
Setting up speedtest-cli (2.1.3-3) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                             
Ukaz: speedtest-cli --secure           
Rezultat: 
Retrieving speedtest.net configuration...
Testing from Telemach (217.72.72.36)...
Retrieving speedtest.net server list...
Selecting best server based on ping...
Hosted by Kapulan Kereskedelmi es Tavkozlesi Kft (Kapuvar) [259.44 km]: 21.611 ms
Testing download speed................................................................................
Download: 88.82 Mbit/s
Testing upload speed......................................................................................................
Upload: 94.41 Mbit/s

Ukaz:  sudo tcpdump -c 10
Rezultat:
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on eth0, link-type EN10MB (Ethernet), snapshot length 262144 bytes
06:31:16.231927 IP 10.0.2.15.52736 > RT-AC1900U-7AD8.domain: 25560+ A? google.com. (28)
06:31:16.232030 IP 10.0.2.15.52736 > RT-AC1900U-7AD8.domain: 12270+ AAAA? google.com. (28)
06:31:16.238908 IP RT-AC1900U-7AD8.domain > 10.0.2.15.52736: 25560 1/0/0 A 142.251.39.14 (44)
06:31:16.238908 IP RT-AC1900U-7AD8.domain > 10.0.2.15.52736: 12270 1/0/0 AAAA 2a00:1450:400d:80c::200e (56)
06:31:16.240520 IP 10.0.2.15 > bud02s37-in-f14.1e100.net: ICMP echo request, id 1, seq 1, length 64
06:31:16.252467 IP bud02s37-in-f14.1e100.net > 10.0.2.15: ICMP echo reply, id 1, seq 1, length 64
06:31:16.252597 IP 10.0.2.15.35686 > RT-AC1900U-7AD8.domain: 54366+ PTR? 14.39.251.142.in-addr.arpa. (44)
06:31:16.255788 IP RT-AC1900U-7AD8.domain > 10.0.2.15.35686: 54366 1/0/0 PTR google.com. (68)
06:31:16.312467 IP 10.0.2.15.48267 > RT-AC1900U-7AD8.domain: 65351+ PTR? 1.2.168.192.in-addr.arpa. (42)
06:31:16.316340 IP RT-AC1900U-7AD8.domain > 10.0.2.15.48267: 65351* 1/0/0 PTR RT-AC1900U-7AD8. (71)
10 packets captured
14 packets received by filter
0 packets dropped by kernel

Ukaz: searchsploit wordpress ftp
Rezultat:
------------------------------------------- ---------------------------------
 Exploit Title                             |  Path
------------------------------------------- ---------------------------------
WordPress Plugin MiwoFTP 1.0.5 - Arbitrary | php/webapps/36774.txt
WordPress Plugin MiwoFTP 1.0.5 - Arbitrary | php/webapps/36801.txt
WordPress Plugin MiwoFTP 1.0.5 - Cross-Sit | php/webapps/36761.txt
WordPress Plugin MiwoFTP 1.0.5 - Cross-Sit | php/webapps/36763.txt
WordPress Plugin MiwoFTP 1.0.5 - Multiple  | php/webapps/36762.txt
------------------------------------------- ---------------------------------
Shellcodes: No Results
                                                                             
Ukaz: dnsenum google.com
Rezultat: prikazani so DNS podatki domene.
dnsenum VERSION:1.3.1

-----   google.com   -----                                                   
                                                                             
                                                                             
Host's addresses:                                                            
__________________                                                           
                                                                             
google.com.                              296      IN    A        142.251.39.14

                                                                             
Name Servers:                                                                
______________                                                               
                                                                             
ns3.google.com.                          66761    IN    A        216.239.36.10
ns4.google.com.                          66524    IN    A        216.239.38.10
ns1.google.com.                          65267    IN    A        216.239.32.10
ns2.google.com.                          22661    IN    A        216.239.34.10

                                                                             
Mail (MX) Servers:                                                           
___________________                                                          
                                                                             
smtp.google.com.                         180      IN    A        142.250.110.26
smtp.google.com.                         180      IN    A        66.102.1.27
smtp.google.com.                         180      IN    A        142.250.110.27
smtp.google.com.                         180      IN    A        142.251.5.27
smtp.google.com.                         180      IN    A        66.102.1.26

                                                                             
Trying Zone Transfers and getting Bind Versions:                             
_________________________________________________                            
                                                                             
                                                                             
Trying Zone Transfer for google.com on ns3.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns4.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns1.google.com ... 
AXFR record query failed: corrupt packet

Trying Zone Transfer for google.com on ns2.google.com ... 
AXFR record query failed: corrupt packet

                                                                             
Brute forcing with /usr/share/dnsenum/dns.txt:                               
_______________________________________________                              
                                                                             
about.google.com.                        300      IN    CNAME    www3.l.google.com.
www3.l.google.com.                       290      IN    A        142.250.201.206
...
  www2.l.google.com.
www2.l.google.com.                       265      IN    A        142.251.38.196
upload.google.com.                       300      IN    CNAME    large-uploads.l.google.com.
large-uploads.l.google.com.              300      IN    A        142.250.201.207
vpn.google.com.                          3600     IN    A        64.9.224.68
vpn.google.com.                          3600     IN    A        64.9.224.69
vpn.google.com.                          3600     IN    A        64.9.224.70
w.google.com.                            300      IN    CNAME    www3.l.google.com....www3.l.google.com.                       250      IN    A        142.250.201.206
www.google.com.                          215      IN    A        142.251.39.4

                                                                             
google.com class C netranges:                                                
______________________________                                             
 8.8.4.0/24                                                                  
 8.8.8.0/24
 64.9.224.0/24
...
 216.239.36.0/24
 216.239.38.0/24
...

Ukaz: lbd google.com    
Rezultat:
lbd - load balancing detector 0.4 - Checks if a given domain uses load-balancing.
                                    Written by Stefan Behte (http://ge.mine.nu)
                                    Proof-of-concept! Might give false positives.

Checking for DNS-Loadbalancing: NOT FOUND
Checking for HTTP-Loadbalancing [Server]: 
 gws
 NOT FOUND

Checking for HTTP-Loadbalancing [Date]: 11:38:05, 11:38:06, 11:38:06, 11:38:06, 11:38:06, 11:38:06, 11:38:07, 11:38:07, 11:38:07, 11:38:07, 11:38:08, 11:38:08, 11:38:08, 11:38:08, 11:38:08, 11:38:09, 11:38:09, 11:38:09, 11:38:09, 11:38:09, 11:38:10, 11:38:10, 11:38:10, 11:38:10, 11:38:11, 11:38:11, 11:38:11, 11:38:11, 11:38:11, 11:38:12, 11:38:12, 11:38:12, 11:38:12, 11:38:13, 11:38:13, 11:38:13, 11:38:13, 11:38:13, 11:38:14, 11:38:14, 11:38:14, 11:38:14, 11:38:15, 11:38:15, 11:38:15, 11:38:15, 11:38:15, 11:38:16, 11:38:16, 11:38:16, NOT FOUND

Checking for HTTP-Loadbalancing [Diff]: FOUND
< Content-Security-Policy-Report-Only: object-src 'none';base-uri 'self';script-src 'nonce-Jg_An3xjjcF61gZsnUxGvQ' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp
> Content-Security-Policy-Report-Only: object-src 'none';base-uri 'self';script-src 'nonce-A24QaSPsQDKGThHTemHjjg' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp

google.com does Load-balancing. Found via Methods: HTTP[Diff]

REFLEKSIJA
- Kali Linux uporabljamo za testiranje varnosti, etični hacking in analizo ranljivosti.
Njegova prednost je velika količina prednameščenih varnostnih orodij.

- Najbolj so me pritegnila orodja Nmap, tcpdump in htop, saj omogočajo dober pregled
omrežja, procesov in sistemskih virov.
