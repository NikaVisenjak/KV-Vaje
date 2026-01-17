# HackyCorp
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl -I https://hackycorp.com/login
curl -I https://hackycorp.com/admin

### /login: 404 Not Found
### /admin: 301 Moved Permanently → preusmeritev na /admin/

```bash 
HTTP/1.1 404 Not Found
Server: nginx
Date: Sat, 17 Jan 2026 19:47:26 GMT
Content-Type: text/html
Content-Length: 108
Connection: keep-alive
ETag: "5ed45a11-6c"
pentesterlab_recon_09: 99d0738b-1e52-4a00-8885-b15894b2c79e

HTTP/1.1 301 Moved Permanently
Server: nginx
Date: Sat, 17 Jan 2026 19:47:26 GMT
Content-Type: text/html
Content-Length: 178
Location: https://hackycorp.com/admin/
Connection: keep-alive
pentesterlab_recon_09: 99d0738b-1e52-4a00-8885-b15894b2c79e
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl https://assets.hackycorp.com/key.txt
```bash
RECON_24: e94ab8a5-b0c1-4559-8bc7-cae2e53b10e0
```
         
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl https://assets.hackycorp.com/js/script.js | grep -i key

### Google API key placeholder: ptlab_key_recon_26: 'd6b75269-97a3-44de-be32-fff0dd55e7ef

``` bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2954 100  2954   0     0 14408     0  --:--:-- --:--:-- --:--:-- 14551
    | Google API Key
    | Here you may specify your Google API key if you need to use Google Maps
    | https://developers.google.com/maps/documentation/javascript/get-api-key
    googleApiKey: '...',
    | this option. Your key would be a value like: UA-12345678-9
    | Please signup for an API key pair and insert your `Site key` value to the
    ptlab_key_recon_26: 'd6b75269-97a3-44de-be32-fff0dd55e7ef',
    reCaptchaSiteKey:  '...',
```


└─$ curl https://hackycorp.com/robots.txt

### Ključ za RECON_00: af9c328a-02b4-439d-91c6-f46ab4a0835b

```bash
User-agent: *
Disallow: /

# You solved recon_00
# The key for this challenge is
# af9c328a-02b4-439d-91c6-f46ab4a0835b 

```

┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl https://hackycorp.com/.well-known/security.txt

### Ključ: 99685e30-7061-4ac0-83bf-4ccc0409faac

``` bash
# Please don't report any security issue for this site
# This is a recon challenge and the key for this exercise is 
# 99685e30-7061-4ac0-83bf-4ccc0409faac
```
                             
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl -I https://hackycorp.com/neobstaja
### 404 Not Found
```
HTTP/1.1 404 Not Found
Server: nginx
Date: Sat, 17 Jan 2026 19:57:40 GMT
Content-Type: text/html
Content-Length: 108
Connection: keep-alive
ETag: "5ed45a11-6c"
pentesterlab_recon_09: 99d0738b-1e52-4a00-8885-b15894b2c79e
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ curl --insecure http://51.158.147.132

### Ključ za RECON_06: 5cf83b5d-eb6c-4eee-af6c-945f9aed8dfd

```bash
<h1>Well done! You solved recon_06 </h1>

The key for this exercise is 5cf83b5d-eb6c-4eee-af6c-945f9aed8dfd
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ git clone https://github.com/hackycorp/repo3.git
cd repo3
git branch -a
```
Cloning into 'repo3'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (6/6), done.
* master
  remotes/origin/08be82ba-e5fd-4fae-b2c2-272a18d31f80
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo3]
└─$ git checkout -b 08be82ba-e5fd-4fae-b2c2-272a18d31f80 origin/08be82ba-e5fd-4fae-b2c2-272a18d31f80

```
branch '08be82ba-e5fd-4fae-b2c2-272a18d31f80' set up to track 'origin/08be82ba-e5fd-4fae-b2c2-272a18d31f80'.
Switched to a new branch '08be82ba-e5fd-4fae-b2c2-272a18d31f80'
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo3]
└─$ cat *
```bash
This is a test
```
                                                                           
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ git clone https://github.com/hackycorp/repo4.git
cd repo4
git branch -a
```bash
Cloning into 'repo4'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (6/6), done.
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/test
```


  ┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo4]
└─$ cat *
```bash
This is the key for recon 21: a60b4aee-642a-483b-9262-ccfc2ed46f0d
Empty.
```
        
┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo9]
└─$ git log -p | grep -E "[a-f0-9]{8}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{12}"
```bash
-This is the key for RECON_22: 3ee505c2-8aa9-4d5e-810e-921778dce1e6
+This is the key for RECON_22: 3ee505c2-8aa9-4d5e-810e-921778dce1e6
```

┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo0a]
└─$ git branch -a  
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
                                                                             
┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo0a]
└─$ git log --oneline --grep=key -i
git log --oneline --grep=secret -i
git log --oneline --grep=flag -i

a35a917 Another test
                                                                             
┌──(kali㉿kali)-[~/KV-Vaje/lab10/repo0a]
└─$ git show a35a917 

### key for RECON_23: 5c75cfe9-52dd-475b-8cfa-7ffc492abeca
```bash              
commit a35a9174f3a6238a8ad70c549287d09e258f087b
Author: Hacky Dev <dev@hackycorp.com>
Date:   Wed Nov 18 11:22:26 2020 +1100

    Another test
    
    This is the key for RECON_23: 5c75cfe9-52dd-475b-8cfa-7ffc492abeca

diff --git a/TEST31.txt b/TEST31.txt
new file mode 100644
index 0000000..e85087a
--- /dev/null
+++ b/TEST31.txt
@@ -0,0 +1 @@
+31
```

┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ dig key.z.hackycorp.com TXT
### TXT ključ: 9f883f22-6ea5-4631-bbe8-95841ad63f56
```bash
; <<>> DiG 9.20.15-2-Debian <<>> key.z.hackycorp.com TXT
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 59751
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;key.z.hackycorp.com.           IN      TXT

;; ANSWER SECTION:
key.z.hackycorp.com.    7200    IN      TXT     "9f883f22-6ea5-4631-bbe8-95841ad63f56"

;; Query time: 104 msec
;; SERVER: 192.168.1.1#53(192.168.1.1) (UDP)
;; WHEN: Sat Jan 17 15:17:44 EST 2026
;; MSG SIZE  rcvd: 97
```

┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ for sub in key test dev txt api admin; do
  dig $sub.z.hackycorp.com TXT +short
done
### Enak ključ za vse poddomene
```
"9f883f22-6ea5-4631-bbe8-95841ad63f56
```

## Razkriti še dodatni TXT ključi:

- RECON_14: e5fce970-6d94-43c1-bdd5-a06c2b235f9c
- VERSION.BIND: 4e5e76e1-728a-49be-aea8-4591ba11e588

┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ dig -t SOA z.hackycorp.com
```

; <<>> DiG 9.20.15-2-Debian <<>> -t SOA z.hackycorp.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 29419
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;z.hackycorp.com.               IN      SOA

;; ANSWER SECTION:
z.hackycorp.com.        298     IN      SOA     ns1.hackycorp.com. ns1.hackycorp.com. 2 604800 86400 2419200 604800

;; Query time: 16 msec
;; SERVER: 192.168.1.1#53(192.168.1.1) (UDP)
;; WHEN: Sat Jan 17 15:19:31 EST 2026
;; MSG SIZE  rcvd: 114
```
                                                                             
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ dig AXFR z.hackycorp.com @ns1.hackycorp.com
```
; <<>> DiG 9.20.15-2-Debian <<>> AXFR z.hackycorp.com @ns1.hackycorp.com
;; global options: +cmd
z.hackycorp.com.        604800  IN      SOA     ns1.hackycorp.com. ns1.hackycorp.com. 2 604800 86400 2419200 604800
z.hackycorp.com.        604800  IN      NS      z.hackycorp.com.
z.hackycorp.com.        604800  IN      A       51.158.147.132
key.z.hackycorp.com.    604800  IN      TXT     "9f883f22-6ea5-4631-bbe8-95841ad63f56"
recon_14.z.hackycorp.com. 604800 IN     TXT     "e5fce970-6d94-43c1-bdd5-a06c2b235f9c"
z.hackycorp.com.        604800  IN      SOA     ns1.hackycorp.com. ns1.hackycorp.com. 2 604800 86400 2419200 604800
;; Query time: 36 msec
;; SERVER: 51.158.147.132#53(ns1.hackycorp.com) (TCP)
;; WHEN: Sat Jan 17 15:20:15 EST 2026
;; XFR size: 6 records (messages 1, bytes 289)
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ dig -c chaos -t txt VERSION.BIND @ns1.hackycorp.com
```
; <<>> DiG 9.20.15-2-Debian <<>> -c chaos -t txt VERSION.BIND @ns1.hackycorp.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 62251
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 1, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
; COOKIE: ffcac4f95edcb917b1ef0857696bef34148cc2f9849867ef (good)
;; QUESTION SECTION:
;VERSION.BIND.                  CH      TXT

;; ANSWER SECTION:
VERSION.BIND.           0       CH      TXT     "4e5e76e1-728a-49be-aea8-4591ba11e588"

;; AUTHORITY SECTION:
version.bind.           0       CH      NS      version.bind.

;; Query time: 40 msec
;; SERVER: 51.158.147.132#53(ns1.hackycorp.com) (UDP)
;; WHEN: Sat Jan 17 15:21:08 EST 2026
;; MSG SIZE  rcvd: 144
```
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ for i in `seq 1 150`
do
  printf "0x%02x.a.hackycorp.com\n" $i >> hosts.txt
done
                                                                             
                                                                             
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ for i in `cat hosts.txt`                           
do
  curl $i/logo.png -o $i.png
done
```
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3476 100  3476   0     0 17953     0  --:--:-- --:--:-- --:--:-- 18010
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3943 100  3943   0     0 35786     0  --:--:-- --:--:-- --:--:-- 35522
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3421 100  3421   0     0 29346     0  --:--:-- --:--:-- --:--:-- 29491
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  4026 100  4026   0     0 34392     0  --:--:-- --:--:-- --:--:-- 34706
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed


...

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3857 100  3857   0     0 24352     0  --:--:-- --:--:-- --:--:-- 24411
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3396 100  3396   0     0 21177     0  --:--:-- --:--:-- --:--:-- 21225
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3784 100  3784   0     0 35409     0  --:--:-- --:--:-- --:--:-- 35698
```

## Preverjanje 

┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ ls -1 *.png | wc -l

150
 
┌──(kali㉿kali)-[~/KV-Vaje/lab10]
└─$ file 0x01.a.hackycorp.com.png
```
file 0x64.a.hackycorp.com.png
0x01.a.hackycorp.com.png: PNG image data, 780 x 100, 8-bit gray+alpha, non-interlaced
0x64.a.hackycorp.com.png: PNG image data, 780 x 100, 8-bit colormap, non-interlaced
```
