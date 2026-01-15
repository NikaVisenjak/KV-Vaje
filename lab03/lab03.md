# Lab03: OSINT – zbiranje informacij o posameznikih na spletu

## Cilj
Spoznati OSINT tehnike in orodja Sherlock in Maigret za zbiranje javno dostopnih informacij o posameznikih.  

---

## Sherlock

**Ukaz za zbiranje informacij o uporabniku "test123":**
```bash
python3 sherlock_project/sherlock.py test123

[*] Checking username test123 on:

[+] 7Cups: https://www.7cups.com/@test123
[+] About.me: https://about.me/test123
[+] Academia.edu: https://independent.academia.edu/test123
[+] Airbit: https://airbit.com/test123
[+] AllMyLinks: https://allmylinks.com/test123
[+] AniWorld: https://aniworld.to/user/profil/test123
[+] Anilist: https://anilist.co/user/test123/
[+] Apple Developer: https://developer.apple.com/forums/profile/test123
[+] Apple Discussions: https://discussions.apple.com/profile/test123
...

maigret test123

[-] Starting a search on top 500 sites from the Maigret database...
[*] Checking username test123 on:
[+] WordPress: https://test123.wordpress.com/
[?] StackOverflow: https://stackoverflow.com/users/filter?search=test123
[+] YouTube User: https://www.youtube.com/@test123
[+] FandomCommunityCentral: https://community.fandom.com/wiki/User:test123
[+] YouTube: https://www.youtube.com/@test123
[+] AppleDiscussions: https://discussions.apple.com/profile/test123
[+] BleachFandom: https://bleach.fandom.com/ru/wiki/%D0%A3%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA:test123
[+] Armchairgm: https://armchairgm.fandom.com/wiki/User:test123
[+] Imgur: https://imgur.com/user/test123
       ├─id: 236006
       ├─imgur_username: test123
       ├─reputation_count: 4.82
       ├─image: https://i.imgur.com/qCjr5Pi_d.png
...
[+] GitHub: https://github.com/test123
        ├─uid: 27031
        ├─image: https://avatars.githubusercontent.com/u/27031?v=4
        ├─created_at: 2008-10-01
        ├─location: Madrid, Spain
        ├─follower_count: 687
        ├─fullname: Avi Dutta
        ├─public_repos_count: 5
        ├─bio: Software Development Manager at Amazon – Madrid
        ├─blog_url: https://www.linkedin.com/in/avidutta/
...
[*] Short text report:
Search by username test123 returned 226 accounts.
Found target's other IDs: 560748468408 (ok_id), 76561197963536013 (steam_id), 114747 (wikimapia_uid).
Extended info extracted from 19 accounts.
Countries: us, ru, in, jp, gb, de, tr, br, kr, tw, id, pl, fr, au, ng, vn, sg, cz, th, ao, ve, es, ph, cn, at, az
Interests (tags): gaming, forum, photo, coding, news, tech, blog, music, sharing, video, writing, wiki, networking, hobby, porn, reading, art, streaming, business, finance, dating, maps, freelance, discussion, books, movies, stock, geosocial, links, messaging, trading, torrent, career, education, documents, sport, hacking

- Maigret je našel veliko profilov, vključno z GitHub, YouTube, TikTok, Facebook, Steam, Disqus, MyMail.ru in drugimi.

Refleksija in analiza

Sherlock je hitro našel osnovne profile uporabnika, medtem ko Maigret vrne bolj podrobne informacije z metapodatki.

Najlažje so bile najdene javne profile na družbenih omrežjih (YouTube, GitHub, Facebook).

Težje je bilo dobiti dodatne podatke (lokacije, identifikatorje, datum registracije).

Potencialna tveganja: razkritje e-poštnih naslovov, profilov, lokacije, biografije in povezav z drugimi omrežji.

Za zaščito lastne zasebnosti: omejitev javno dostopnih podatkov, uporaba zasebnih nastavitev, neuporaba enakih uporabniških imen za vse storitve.

OSINT orodja so etična za analizo lastnih digitalnih odtisov ali za etične raziskave. Ne smemo zbirati ali zlorabljati podatkov drugih brez dovoljenja.
