# Lab4

Cilj četvrti laboratorijski vježbi je na pravom praktičnom primjeru probati kriptirati određenu šifru i pomoću nje izvršiti autentifikaciju određene poruke. 

Koristimo simetrični kriptografski MAC algoritam, točnije HMAC HMAC mehanizam iz Python biblioteka `[cryptography](https://cryptography.io/en/latest/hazmat/primitives/mac/hmac/)`.

- Iz biblioteke smo izvukli funkciju za proračun i provjeru MAC vrijednosti

Zatim smo imali lokalno pojedinačne izazove tj. tekstualna datoteka koja predstavlja transakcijske naloge i datoteka sa MAC tag-ovima. Naš zadatak je bio provjeriti je li se nalog i njemu sukladan MAC tag podudaraju.

- Prvo saznamo vrijednost koja se koristi kao ključ uz pomoć imena i prezimena
    
    `key = "<prezime_ime>".encode()`
    
- Uz pomoć petlje iskopirali smo kod koji provjerava slaže li se key sa provjerenom MAC vrijednosti. U slučaju da, ispisuje pored naloga OK, suprotno NOK.

Treći dio zadatka nismo stigli na vježbama.