Lab00: Uvod v Linux

Cilj
Naučiti se osnovnega dela z ukazno vrstico v Linux okolju.

Priprava okolja
VirtualBox Kali Linux VM
Dostop do terminala

Ukazi, ki sem jih uporabil/a:

Krmarjenje po sistemu
cd ~
mkdir linux-vaja
cd linux-vaja

Delo z datotekami in imeniki
touch opis.txt
nano opis.txt      # vpisala sem svoje ime, CTRL+O za shranjevanje,ENTER, CTRL+X za izhod
mkdir testni
mv opis.txt testni/

Premikanje in kopiranje
mv testni/opis.txt testni/moj_profil.txt
cp testni/moj_profil.txt ~/

Pravice in velikosti
ls -lh
du -sh ./*
chmod 444 testni/moj_profil.txt

Sistemskih informacij
whoami
du -sh ~
df -h
top      # q za izhod iz top

Dodatna naloga – največje datoteke
du -ah ~ | sort -rh | head -n 5

Rezultati
Ime uporabnika: kali
Velikost domačega imenika: 2.8M /home/kali
Razpoložljiv prostor na disku: /dev/sda1  50G  10G  38G  21% /

Najvecje datoteke: 	
	2.4M /home/kali
	1.5M /home/kali/.cache
	1.4M /home/kali/.cache/gstreamer-1.0/registry.x86_64.bin 
	1.4M /home/kali/.cache/gstreamer-1.0
	520K /home/kali/KV-Vaje


