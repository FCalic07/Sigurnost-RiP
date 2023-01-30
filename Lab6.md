# Lab6

## **Online and Offline Password Guessing**

### **Kao prvi dio labova odradili smo online password guessing.**

- Spojili smo se na lokalnu mrežu te pomoću ssh klijenta pokušali spojit na svoj server koji su u formatu prezime_ime@prezimeime.local
- Server od nas traži lozinku/password koju ne znamo
- Koristimo `hydra` aplikaciju za brute-force potragu za lozinkom.
    
    Opet da bi nekako smanjili vrijeme napada vodimo se da znamo dvije stvari u vezi lozinke.
    Ima 4-6 lowercase slova.
    To bi idalje bilo circa $26^6$, odnosno preko 300 000 000 mogućih lozinki
    Na mom prijenosnom računalu *hydra* je radila stopom 64 pokušaja po minuti
    To znači da je veliko O, ilitiga za najgori slučaj, potrebno blizu 9 godina.
    
- Zato smo koristili dictionary koji iskorištava mane ljudskog odabira lozinki
    
    `wget -r -nH -np --reject "index.html*" http://challenges.local/dictionary/g3/`
    
    `hydra -l calic_filip -P dictionary/g3/dictionary_online.txt calicfilip.local -V -t 4 ssh`
    

Nakon par minuta uspješno smo saznali lozinku   (*sbears*)

### **Za drugi dio vježbe simulirali smo offline password guessing**

- Služimo se `hashcat` alatom koji crackira hash vrijednosti lozinki
- Dobili smo listu korisnika i korisničke hash vrijednosti u formatu 
*$$***id***$$***salt***$$***hash_value**.
- Opet proces bi bio predug (iako puno kraći nego kod online napada) da nemamo
dictionary

`hashcat --force -m 1800 -a 0 pwd_hash.txt dictionary/g3/dictionary_offline.txt --status --status-timer 10` 

Opet smo uspješno saznali lozinku i prijavili se kao *freddie_mercury*