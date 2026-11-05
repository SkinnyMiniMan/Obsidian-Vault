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

.split() deli glede na beli prostor, lahko mu damo 

