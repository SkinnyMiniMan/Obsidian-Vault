<div> 
	<div style="float: left;">
		<a class="internal-link" href=#>◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 2">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

večbesedna imena -> podčrtaji med besedami

// -> celosštevilsko deljenje
** -> potenciranje

x = y -> x in y kažeta na isti podatek ("škatlico"), ob spremembi ene od spremenljivk si ta spremenljivka ustvari nov podatek

mat funkcije:
`{python icon} from math import *`

NE DAJ NIČESAR NA PRINT
PRINT = 15 JE PREPOVEDANO
lahko pa daš print na drugo spremenljivko

stringa in inta ne seštevamo s +, lahko seštevamo dva stringa, z + lahko:
- int in int
- int in float
- str in str

str * 0 = prazen str
str * int = str se ponovi tolikokrat kot je int

int(True) = 1
float() in int() funkciji sprejmeta niz in ga spremenita v int/float
str() iz int/float/bool... vrne string

input() -> vpraša po inputu

```run-python title:"BMI" header:"shown"
visina = float(input("Telesna višina [m]: "))
teza = float(input("Teža [kg]: "))
bmi = teza / (visina ** 2)

print("Indeks vaše telesne mase je", round(bmi, 1),".")
if bmi > 25:
	print("Potrebno bo shujšati!")
elif bmi == 25:
	print("Ni potrebno shujšati.")
else:
	print("Potrebno se bo zrediti!")
```

primerjava dveh podatkov: <, >, ==, <=, >=, !=

if -> elif -> else

Operatorji:
	+ - * / %  ->  aritmetični operatoriji
	<, >, ==, <=, >=, !=  ->  logični operatorji  ->  vrne True/False  ->  bool (boolean)

bool:
- bool(2) = True
- bool(-1) = True
- bool(0) = False
- bool(0.0) = False
- bool("") = False

if pokliče bool od izraza

`{python icon} if pretezak == True` -> ne tega pisat
`{python icon} if pretezak` -> raje tako

`{python icon} if pretezak == False` -> ne tega pisat
`{python icon} if not pretezak` -> raje tako