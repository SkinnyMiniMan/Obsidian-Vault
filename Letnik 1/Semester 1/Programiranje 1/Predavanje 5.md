<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 4">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 6">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

Regularni izrazi so uporabni, ne bomo se jih učili

.lower() -> vse črke niza spremeni v male črke
.upper() -> velike črke
.count("#") -> prešteje kolikokrat se # pojavi (lahko tudi ".#")


ime = "benjamin"
"enj" in ime -> pove če se "enj" pojavi v ime

ime.find("enj") -> najde na katerem mestu je "enj"
ime.index("enj") -> isto kot .find() 
RAZLIKA: .find() vrne -1 če ne najde, .index() vrne napako
```python
def zamenjaj(s):
	i = s.find("jam")
	return s[:i] + "jem" + s[i+3:]
#zamenja jam z jem, če ne najde jam potem dela velike probleme, ker je rezultat -1; zato moramo uporabiti index, da se rezultat sesuje tukaj, ko se dejansko zgodi napaka, ne pa da se napaka prenaša dalje v program
#Bert -> Bertjemrta
```
ime.find() -> gleda iz leve proti desni, najde prvega
ime.rfind() -> glede iz desne proti levi, najde prvega
ime.rjust(20) -> doda presledke na desno, toliko da je 20 znakov
ime.ljust(20) -> doda presledke na levo, toliko da je 20 znakov

.strip() -> izbrise vse presledke iz leve in desne, vmesne pusti
.strip(".") -> izbriše vse "." iz leve in desne, vmesne pusti
.rstrip() in .lstrip() -> briše iz leve/desne
niz čez več vrstic, ki lahko  vsebuje narekovanje:
""" ali '''
niz
""" ali '''

.split() -> razbije niz na seznam besed
.count("pač") -> prešteje vse pojave črk "pač" (tudi če so znotraj besede)
.split().count("pač") -> prešteje besede pač

.split() deli glede na beli prostor, lahko mu damo argument
.split(", ") deli glede na vejice
NE PISATI .split(" ") -> ni dobro, ker se drugače obnaša, najde prazne nize

" in ".join(imena) -> "Ana in Berta in Cilka in Dani" -> združi elemente seznama in med elemente da in
UPORABNO:
```python
", ".join(imena)
", ".join(imena[:-1]) + " in " + imena[-1]
```

.replace("min", "max") -> Benjamin postane Benjamax, ampak ne spremeni niza, le vrne eno nov niz
ime = ime.replace("min", "max")

s.replace("  ", " ") -> zamenja dva presledka z enim, lazy rešitev:
s.replace("  ", " ").replace("  ", " ").replace("  ", " ").replace("  ", " ").replace("  ", " ") -> če imamo veliko nepotrebinih presledkov (do 32), jih bo spremenilo v enojne

"".join(imena) -> več imen v seznamu združi v en niz

.endswith(".mov") -> uporabno za file types
.startswith() -> preveri s čim se začne

help(str) -> pomoč (dokumentacija)

NA IZPITU IMAMO LAHKO VSO LITERATURO oz. DOKUMENTACIJO ZA PYTHON, tako da nam tega tega ni treba znat, le zavedat se moram da obstaja
NA IZPITU IMAMO kompletno dokumentacijo, internet bo zaprt, učilnica bo videna, gor bo pdf z kompletno dokumentacijo pythona (2353 strni btw), rešitve vseh domačih nalog....

Metode seznamov (seznami se dajo spreminjat, nizi pa ne)
.append("Ema") -> doda 1 element na konec seznama
.extend(["Fanči", "Greta"]) -> doda 2 stvari; isto kot imena += ["Fanči", "Greta"]
.append(["Fanči", "Greta"]) -> doda seznam na konec seznama
imena += "Jana" -> doda črke J, a, n, a; extend dela isto;
imena += ["Jana"] -> doda en element na konec; isto kot append (raje uporabi append)

.count() -> isto kot pri nizih

.find() ne obstaja pri seznamih le **.index()**
če ima seznam več istih spremenljivk, potem vrne prvo ki se ujema argumentu
.index() je počasen :(
.index() slander :(

.remove() -> uporabimo ko ne vemo kje je stvar ki jo želimo pobrisat in/ali nam je vseeno katero od ponovitev izbrišemo
.pop() -> vrne zadnje ime in ga pobriše
.pop(1) -> vrne in izbriše na indeksu 1
del imena[2] -> pobriše element na indeksu 2, ni funckija, je operator

.remove() -> zahteva elemnt
.pop() in del potrebujeta indeks

Če brišeš elemente v seznamu pojdi od konca proti začetku (če uporabljaš range)
ali
uporabi while (while i < len(osebe)) in ne prištej 