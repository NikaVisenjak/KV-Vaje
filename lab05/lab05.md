### Analiza phishing sporočila – Prevzem paketa

**Sumljivi znaki:**
- Pošiljatelj uporablja domeno `postapaket.xyz`, ki ni uradna domena Pošte Slovenije
- Povezava vodi na domeno `.ru`, kar ni povezano s slovensko pošto
- Uporabljen je pritisk časa (24 ur)
- Sporočilo nima osebnega nagovora

**Zaključek:** Gre za phishing napad, ki izkorišča pričakovanje paketa in občutek nujnosti.

### Analiza phishing sporočila – Bančni račun

**Sumljivi znaki:**
- Domeno `bankaa-si.com` banka ne uporablja
- Banke nikoli ne zahtevajo potrditve podatkov preko e-pošte
- Grožnja z deaktivacijo računa
- Sumljiva povezava brez uradne domene

**Zaključek:** Phishing napad z izkoriščanjem strahu in avtoritete.

### Analiza phishing sporočila – Nagrada

**Sumljivi znaki:**
- Uporabnik ni sodeloval v nagradni igri
- Zahteva po plačilu "simbolične pristojbine"
- Neznana domena `promocije.win`
- Psihološki pritisk (navdušenje, pohlep)

**Zaključek:** Phishing napad, ki cilja na radovednost in željo po nagradi.

## 4. Preverjanje phishing sporočila v Linux okolju

Analiza je bila izvedena z uporabo simulirane phishing e-pošte v `.eml`
obliki, ustvarjene in analizirane v Linux terminalu.

### 4.1 Ustvarjanje testnega phishing sporočila

Ukaz: nano paket.eml
V datoteko je bila vnesena simulirana vsebina e-pošte skupaj z
e-poštnim headerjem.

### 4.2 Pregled e-postnih headerjev

Ukaz: sed '/^$/q' paket.eml
Rezultat: 
From: "Pošta Slovenije" <dostava@postapaket.xyz>
Return-Path: <scam@paket-secure.ru>
Received: from unknown (185.234.72.19)
    by mail.fake-server.net with SMTP;
Date: Tue, 14 Jan 2026 09:12:00 +0100
Subject: Vaš paket čaka na dostavo!

- polje From (dostava@postapaket.xyz) se ne ujema z Return-Path (@paket-secure.ru)
- zaznan je sumljiv IP naslov pošiljatelja
- e-pošta je bila posredovana preko neznanega strežnika

### 4.3 Preverjanje IP naslova posiljatelja

Ukaz: whois 185.234.72.19
- IP naslov pripada ponudniku gostovanja DeinServerHost
- država izvora: Nemčija (DE)
- IP ne pripada uradni instituciji (Pošta Slovenije)
- Uporaba tujega gostovanja za slovensko institucijo predstavlja močan
indikator phishing napada.

Abuse contact for '185.234.72.0 - 185.234.72.255' is 'abusecontact@deinserverhost.de'

inetnum:        185.234.72.0 - 185.234.72.255
netname:        DSH-1
org:            ORG-DEIN1-RIPE
country:        DE
admin-c:        CRH20-RIPE
tech-c:         CRH20-RIPE
status:         ASSIGNED PA
mnt-by:         DeinServerHost
created:        2019-02-18T06:41:36Z
last-modified:  2019-02-24T13:36:06Z
source:         RIPE

organisation:   ORG-DEIN1-RIPE
org-name:       DeinServerHost
org-type:       OTHER
address:        Grubenstraße 21
address:        66265 Heusweiler
address:        Deutschland
abuse-c:        ACRO20307-RIPE
admin-c:        CRH19-RIPE
mnt-ref:        MNT-HOSTUS
mnt-by:         MNT-HOSTUS
created:        2018-11-14T12:46:15Z
last-modified:  2018-11-14T12:46:15Z
source:         RIPE # Filtered

person:         Christian Ralph Hennig
address:        Kirchplatz 17
address:        66571 Eppelborn
address:        Germany
phone:          +49-68815959100
nic-hdl:        CRH20-RIPE
mnt-by:         DeinServerHost
created:        2019-02-14T00:56:49Z
last-modified:  2022-04-09T21:33:37Z
source:         RIPE

% Information related to '185.234.72.0/24AS213250'

route:          185.234.72.0/24
origin:         AS213250
mnt-by:         DeinServerHost
created:        2022-02-26T00:44:24Z
last-modified:  2022-02-26T00:44:24Z
source:         RIPE
...

### 4.4 Preverjanje domene posiljatelja

Ukaz: whois postapaket.xyz
Rezultat: 
The queried object does not exist: DOMAIN NOT FOUND
- domena ne obstaja oziroma ni registrirana

### 4.5 Preverjanje SPF, DKIM in DMARC zapisov

Ukaz: grep -i "spf\|dkim\|dmarc" paket.eml
Rezultat: v e-poštnem headerju ni prisotnih SPF, DKIM ali DMARC zapisov
- Manjkajoči varnostni zapisi dodatno potrjujejo, da sporočilo ni legitimno.

### Primer phishing sporocila
Tip napada: Phishing
Cilj: Kraja gesla
Psihološki vzvodi: strah, nujnost, avtoriteta

#Opis

Sporočilo se predstavlja kot obvestilo IT-podpore o domnevni varnostni
težavi z uporabniškim računom. Uporablja uraden videz, logotip organizacije
in zahteva takojšnje ukrepanje.

#Značilnosti:
- splošen nagovor
- sumljiva domena pošiljatelja
- pritisk časa
- povezava do lažne prijavne strani

### Refleksija
Sumljivo e-poštno sporočilo je pogosto mogoče prepoznati že zelo hitro,
če smo pozorni na pošiljatelja, povezave in način komunikacije.

Brez analize e-poštnih headerjev ni vedno mogoče z gotovostjo potrditi,
ali je sporočilo nevarno, zato je tehnična analiza pomemben del
prepoznavanja phishing napadov.

Novim uporabnikom elektronske pošte bi svetovala:
- naj ne klikajo na sumljive povezave
- naj ne delijo gesel ali osebnih podatkov
- naj preverjajo domene pošiljateljev
- naj v primeru dvoma preverijo informacije pri uradnem viru
