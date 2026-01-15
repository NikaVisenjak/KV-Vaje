## gesla.txt
	Password1
	qwerty123
	My$Strong&Pass2024
	letmein
	Summer2024

## Ukaz 
n=1; while read pass; do echo "user$n:$(echo -n "$pass" | md5sum | awk '{print $1}')"; n=$((n+1)); done < gesla.txt > hashes.txt

> cat hashes.txt
	user1:2ac9cb7dc02b3c0083eb70898e549b63
	user2:3fc0a7acf087f549ac2b266baf94b8b1
	user3:d09b2f134b49212fb6966b5d337047e5
	user4:0d107d09f5bbe40cade3de5c71e9e9b7
	user5:e90664c0af74160644d29e4d6147969b

### NAPAD

Ukaz: john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
Rezultat:
	Using default input encoding: UTF-8
	Loaded 5 password hashes with no different salts (Raw-MD5 [MD5 128/128 SSE2 4x3])
	Warning: no OpenMP support for this hash type, consider --fork=2
	Press 'q' or Ctrl-C to abort, almost any other key for status
	letmein          (user4)     
	qwerty123        (user2)     
	Password1        (user1)     
	3g 0:00:00:01 DONE (2026-01-15 08:38) 2.439g/s 11661Kp/s 11661Kc/s 23327KC/s  filimani..*7¡Vamos!
	Use the "--show --format=Raw-MD5" options to display all of the cracked passwords reliably
	Session completed. 

Ukaz: john --show --format=raw-md5 hashes.txt
Rezultat: 
	user1:Password1
	user2:qwerty123
	user4:letmein

	3 password hashes cracked, 2 left
	
### ANALIZA
Razbita so bila gesla, ki so kratka, pogosto uporabljena in prisotna v slovarjih. 
Nerazbita gesla:
- My$Strong&Pass2024
- Summer2024

Daljše geslo bistveno poveča čas razbijanja.
Posebni znaki zmanjšajo možnost, da je geslo del slovarja.
Passphrase je pogosto varnejša in lažje zapomljiva kot kratko geslo.
Priporočljivo je uporabljati dolga, edinstvena gesla z različnimi tipi znakov
Močno geslo z veliko dolžino, posebnimi znaki in nepredvidljivo strukturo ni bilo najdeno v wordlistu, kar potrjuje pomen kompleksnosti.

Vaja je pokazala, da so slabo izbrana gesla izjemno ranljiva, tudi če so shranjena kot zgoščene vrednosti. Uporaba dolgih, kompleksnih gesel in sodobnih hash algoritmov je ključna za zagotavljanje varnosti uporabniških računov.
