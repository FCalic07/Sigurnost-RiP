# Lab3

Na trećim laboratorijskim vježbama tema je bila Symmetric key cryptography.
Cilj vježbe bio je dobiti plaintext od odgovarajućeg ciphertexta bez prethodnog
poznavanja ključa.

**Symmetric key cryptography**

Cilj trećih laboratorijskih vježbi je dešifrirati odgovarajući cyphertext.

Korištena je Python biblioteka `[cryptography](https://cryptography.io/en/latest/)`, a plaintext je enkriptiran korištenjem sustava Fernet iz navedene  `[cryptography](https://cryptography.io/en/latest/)` biblioteke.

Na linku [http://challenges.local/](http://challenges.local/) nalazile su se enkriptirane datoteke (imena i prezimena
studenata). Svaki student je uz pomoć koda koji smo pisali s profesorom pronašao
svoje ime i prezime.

Koristili smo Brute-force napad

- Kroz više iteracija dekripcijskim algoritmom pokušajemo dekriptirat ciphertext
- Funkcija test_png koja provjerava odgovarajuli prva 32 bita plaintexta headeru datoteke .png
- Ako da, znamo ključ i dobijemo plaintext u obliku png formata