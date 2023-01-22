# Lab5

Password hashing, odnosno autentifikacija korisnika putem lozinke

- Poredili smo vrijeme izvršvanja kriptografskih funkcija
- Napravili jednostavan register user i log-in user sustav

## Usporedba vremena

- Kriptografske funkcije: **AES**, **HASH_SHA256** i **HASH_MD5**

Rezultat je da HASH_SHA256 i HASH_MD5 su brže od AES.

Problem kod hash funkcija je u tome što su mogući napadi tipa dictionary attack gdje napadač sastavi rječnik svih najčešćih riječi, kombinacija u lozinkama ili iskoristi listu lozinki za koje se zna da su bile korištene (ima tog na Internetu). Time napadač spremi listu hash vrijednosti tih lozinki i smanji si vrijeme napada. Rješenje tome je iterativna metoda gdje spremamo hash vrijednost na n-tu . Tako da za svaku x hash vrijednost je potrebna x-1 hash vrijednost. To naravno usporava proces napada.

## Register/Log-in

- Programirali smo idalje u Phytonu, instalirajući biblioteke iz `requirements.txt`
- Koristili smo Argon2 funkciju

Funckija Argon2 sprema u hash vrijednost sol i koristi ju za razlikovanje dva korisnika makar imali istu lozinku. 

Također sol služi da osnaži ‘’slabe’’ lozinke jer je u teoriji nasumična i zajedno s lozinkom ide u hash funkciju time dajući drugačiju hash vrijednost

Dodatna opreznost/funkcionalnost je da pri pogrešnom unosu podataka program izbaci poruku da je pogrešno unesena **lozinka ILI korisničko ime.** Time napadač ne zna točno ima li nešto od tog dvoje u bazi podataka. Iako detaljnije o tome, može se saznat usporedbom vremena dolaska povratne informacije jer program uspoređuje char po char. Također sve podatke unesene smo pogledali kako u pozadini se unose u bazu podataka.