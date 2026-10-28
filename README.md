# FS Rules Academy 2026 v1.1 — PRO

Dvojezična (HR/EN) web-aplikacija za učenje iz korisnikove skripte **FS Rules 2026 v1.1**.

## Sadržaj i provjera

- **57/57** pravila iz dostavljenog teksta: T11.1.1–T11.1.8, EV1.1–EV1.2, EV2.1–EV2.2, EV3.1–EV3.2, EV4.1–EV4.3 i EV5.1–EV5.3.
- **18/18** pojmova (uključujući VCU, AIR, BSPD, AMS, TS, LVS, itd.).
- **Tablica 5**: svi izvorni podaci za četiri naponska raspona.
- **162** sadržajno određena dvojezična pitanja, s najmanje jednim specifičnim pitanjem za **svako** od 57 pravila; **12** pitanja za sve vrijednosti Tablice 5; **26** pitanja s primjerima primjene.
- **103** pitanja imaju oznaku VCU/LV prioriteta. Kratki prioritetni ispit od 15 pitanja svaki put uključuje po jedno pitanje iz **svake** odredbe T11.1 (8), 4 pitanja iz povezanih EV odredbi, jedno VCU pitanje te 2 pitanja iz važnih povezanih pojmova.
- Miješani ispit od 20 pitanja pokriva svako od šest glavnih poglavlja (T11, EV1–EV5) uz tablicu i pojmovnik.
- Točni odgovor, objašnjenje i poveznica na relevantnu odredbu prikazuju se nakon odgovora.
- Učenje, pretraživanje, oznaka naučeno, ponavljanje pogrešaka, rezultat, povijest i JSON izvoz/uvoz napretka.
- Instalacija kao **PWA** i rad bez mreže nakon prvog učitavanja, ovisno o pravilima instalacije preglednika.

## Izvor i tumačenje

`SOURCE_EN_HR.txt` je kopija datoteke koju je dostavio korisnik. Tekst svakog pravila u `data.js` unesen je bez preformuliranja izvornog EN ili HR sadržaja. Na stranicama aplikacije oba su jezika vidljiva zajedno.

**Napomena:** ovo je izvadak i edukativna skripta, a **nije cijeli službeni Formula Student Rules 2026**. Engleski izvor mjerodavniji je od informativnog prijevoda. VCU se pojavljuje kao pojam u pojmovniku, ne kao samostalno službeno pravilo u dostavljenom izvatku. Pitanja o VCU primjenjuju stvarne zahtjeve drugih odredbi, ne uvode nova službena VCU pravila. Pri projektiranju vozila koristite cijeli aktualni službeni pravilnik.

## Postavljanje na GitHub Pages

1. Raspakirajte ZIP.
2. Prenesite **sve datoteke unutar ZIP-a** u korijenski direktorij repozitorija `fs-rules-academy` na GitHubu, zamjenjujući staru verziju (`index.html`, `app.js`, `styles.css`, `sw.js`, `data.js` itd.).
3. U **Settings → Pages** odaberite **Deploy from a branch**, `main`, folder `/ (root)`, ako nije već konfigurirano.
4. Otvorite `https://lukajakus.github.io/fs-rules-academy/`.
5. Ako i dalje vidite staru verziju, osvježite stranicu (po potrebi zatvorite pa ponovno otvorite instaliranu PWA); izvorne datoteke u repozitoriju moraju biti nove.

Aplikacija je statički HTML/CSS/JS. Ne zahtijeva server, API ključ ni račun za korištenje.

## Tehnička provjera

Izvršeno: `node --check` nad tri JS datoteke; provjera strukture 57 pravila, 18 pojmova i 162 pitanja; testiranje putem Chromium/Playwright s injiciranim lokalnim resursima (normalna mrežna navigacija bila je ograničena u testnom okruženju). Testiran potpuni ispit od 162 pitanja, kratki ispit, Tablica 5, filtriranje, pretraživanje, HR↔EN, napredak, bez JavaScript pogrešaka. Stvarni iPhone/Safari i GitHub Pages deployment nisu testirani.

Detalji broja pitanja po odredbi su u `audit.json`.
