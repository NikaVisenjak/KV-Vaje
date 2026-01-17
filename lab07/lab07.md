### (1) Priprava testnega phishing obrazca

## nano login.html
```bash
<!DOCTYPE html>
<html lang="sl">
<head>
<meta charset="UTF-8">
<title>Prijava</title>
</head>
<body>
<h2>Prijava v sistem</h2>
<form method="POST" action="">
  Uporabniško ime: <input type="text" name="username"><br>
  Geslo: <input type="password" name="password"><br>
  <input type="submit" value="Prijava">
</form>
</body>
</html>
```
## Posnetek zaslona lažne prijavne strani

![Lažna prijavna stran](screenshots/login_page.png)

## Posnetek zaslona lažne prijavne strani - kopija
tehnicne zadeve - ni delovalo po korakih 1, 2, 3, 2 --> zadni korak sem dala 3 (custom), kjer se more uporabit index.html
![Kopija](screenshots/index_page.png)

### (2) Zagon SET in kloniranje
![SET01](screenshots/korak_1.png)
![SET02](screenshots/korak_2.png)
![Klonirana stran](screenshots/klonirana_stran.png)

## zagon 
```bash
firefox http://10.0.2.15
```
-> VPIS PODATKOV "test" in "geslo123"

### (3) Rezultat - zajeti podatki
![Zajeti_podatki](screenshots/zajeti_podatki.png)

### (4) ANALIZA, REFLEKSIJA in POROCILO
- posnetki ze dodani zgoraj.

# Phishing strani imajo pogosto naslednje značilnosti:
- napačen ali sumljiv URL naslov
- pomanjkanje HTTPS in varnostnih certifikatov
- zelo preprost dizajn
- zahteva po vnosu občutljivih podatkov brez dodatne preverbe
- hitro zahtevajo vnos podatkov, da uporabnik ne opazi opozoril

# Uporabniki se lahko zaščitijo z:
- preverjanjem URL naslova
- uporabo upravljalnikov gesel
- dvostopenjsko avtentikacijo
- previdnostjo pri povezavah iz e-pošte

Moderne spletne strani otežujejo phishing napade z uporabo HTTPS,
CSRF zaščite, Content Security Policy (CSP) in dodatnih preverjanj
pristnosti uporabnika

