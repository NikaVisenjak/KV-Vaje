# Lab04: MetaOSINT – Kaj vse razkrije fotografija?

## Cilj
Analiza EXIF metapodatkov fotografij za razumevanje, koliko informacij slike lahko razkrijejo o času, napravi, lokaciji in obdelavi.

---

## Izvedba

### Izbrana fotografija
Testna slika: Nikon_D70.jpg (kopirana iz `exif-samples/jpg/`)

### Ukaz za pridobivanje EXIF podatkov
```bash
exiftool Nikon_D70.jpg

### Izpis in analiza

Make: NIKON CORPORATION

Camera Model Name: NIKON D70

Date/Time Original: 2008:03:15 09:52:01

Software: GIMP 2.4.5

Creator Tool: Adobe Photoshop CS2 Windows

Exposure Time: 1/200

F Number: 9.0

ISO: 200

Focal Length: 100.0 mm

Orientation: Horizontal (normal)

Comment: comment in GIMP 2.4.5

Dodatni podatki:

Shutter Speed Value: 1/200

Aperture Value: 9.0

Exposure Compensation: -1

Flash Fired: False

Image Width x Height: 100x66 px

Lens: 100.0 mm f/2.8

White Balance: As Shot

Color Space: sRGB

### Refleksija in porocilo

Fotografija razkriva natančno napravo in model kamere, čas posnetka in programsko opremo, ki je bila uporabljena za obdelavo.

Potencialna tveganja: če bi slika vsebovala GPS koordinate, bi bilo mogoče določiti natančno lokacijo, kar predstavlja zasebnostno tveganje.

Najbolj zanimivo je bilo videti, da EXIF vsebuje tudi podatke o programski obdelavi slike (GIMP, Adobe Photoshop)

### Nasveti za zascito podatkov
Pred objavo slik odstranimo EXIF metapodatke:
exiftool -all= -overwrite_original Nikon_D70.jpg
Uporabimo spletna orodja za testne primere:
	https://www.verexif.com/en/
	https://www.exifremove.com/
Bodimo pozorni, katere slike vsebujejo lokacijo ali občutljive podatke.

### Refleksija
- Vsak, ki redno objavlja slike na spletu, naj razmisli o odstranitvi metapodatkov, da zaščiti svojo zasebnost.
- EXIF podatki lahko razkrijejo lokacijo, čas, napravo in druge podatke, kar je pomembno za varno rabo digitalnih vsebin.
- Uporaba orodij kot exiftool pomaga ozavestiti, koliko informacij je lahko skritih v fotografijah.
