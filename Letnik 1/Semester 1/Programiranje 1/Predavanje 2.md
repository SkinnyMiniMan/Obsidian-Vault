<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 2">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 3">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

Vsi uporabni jeziki v if stavku gledajo le prvega pri OR, le če je prvi napačen gre pogledat drugega
Primer:
```run-python
if 15 == 15 or 1/0 == -1/12:
	print("Preveril sem le prvi, če bi tudi drugega bi se program zlomil")
```

Isto deluje za AND, če je prvo neresnično nebo gledalo drugega, aka kot da bi storil if v if, to nam lahko pomaga pred izpadom kode (npr. deljenje z 0)

```run-python
x = 8
a = 3
s = "" #to je neresničen stavek

print(x or a)
print(a or x)
print(s or x)

print(4 and 3 or 5)
print(3 and 0 or 5)
```
Razlaga kode:
Vedno gre iz leve proti desni je, zato vedno izpiše prvo spremenljivko če je resnična, drugače drugo (isto dela od leve proti desni z tremi)
3 and 4 or 5 izpiše drugo spremenljivko pir ANDu, če je katerakoli od dveh izrazov neresničen (0), potem izpiše 5, aka gre tako: ((4 and 3) or 5)

a if x = 8 else b -> japonska koda isto kot:
```run-python
a if x == 8 else b

if x == 8:
	a
else:
	b
```

True = 1
False = 0
True + True = 2

kako preštejemo koliko števil je enakih 8?
```run-python
x = 8
y = 4
z = 8

print((x == 8) + (y == 8) + (z == 8)) #True + False + True

print("Peter" * (x == 8)) #izpiše Peter, le če je x enak 8
```
Pazi!!! Moraš imeti oklepaje!!! Drugače ima + prednost

Python ni hiter jezik, če potrebuješ hitrost uporabi knjižnice!! npr. numpy
Ne uporabljaj LISTov kadar bi bilo boljše DICTe

V Pythonu se spremenljivke nanašajo na objekte, v C pa na lokacijo bitov

Seznami:
sej znaš po večini

Seznam seznamov
```python
sez_sez = [[75, "Anže", False], [68, "Blert", True]]

from math import *
funkcije = [sin, cos, tan]
```

Sezname lahko seštevamo, množimo...

`{python icon} from random import shuffle`
`{python icon} sorted([1, 4, 5, 2, 6, 8, 9, 3])` -> vrne sortiran seznam

Nize primerja in ureja po abecedi (prvi črki)

Vejica (,) na koncu seznama ni prepovedana,

Terke:
`{python icon} oseba = (74, "Anze", False)`

```run-python
oseba = (74, "Anze", False)

teza, ime, je_zenska = oseba #razpakiranje
print(teza)
print(ime)
print(je_zenska)
```

Razpakiram lahko tudi druge stvari (sezname, stringe)

`{python icon} a, b, c, d, e, f, g = "abcefg"`

`{python icon} x, y = y, x` -> zamenja spremenljivki

```run-python
imena = ["a", "b", "c", "d"]
for i in imena:
	print(i)
```
i je pointer v tabeli, ne pa število

```run-python
imena = ["a", "b", "c", "d"]
for i in range(len(imena)):
	print(imena[i])
```
tukaj je i števec ki se viša dokler ne pride do dolžine tabele imena

```run-python
for i in range(0, 5, 2):
	print(i)
```
range(začetek(0), dolžina(5), korak(+2))

```run-python
teze = [75, 68, 70, 84, 70, 66]

vecji_od_80 = False #zastavica/flag
for teza in teze:
	if teza > 80:
		vecji_od_80 = True
		break #ko najde enega potem konca delat for
```

```run-python
teze = [75, 68, 70, 79, 70, 66]

vecji_od_80 = False #zastavica/flag
for teza in teze:
	print(teza)
	if teza > 80:
		print("Nekdo je težji od 80")
		break
else:
	print("Vsi so lažji od 80")
```
else -> Če se zanka konča z breakom potem se else NE izvede, če se break ne zgodi se else zgodi
Break prekine zanko -> else se izvede
Break NE prekine zanke -> else NE prekine zanke

Če ni IFa potem tisti else ne dela

for zanka (for x in seznam_terk), se x nanaša na celo terkož
```run-python
podatki = [
	(74, "Anze", False),
	(75, "Blerta", True),
	(66, "Marjetka", True),
]

for oseba in podatki:
	teza, ime, je_zenska = oseba #delaj tako
	print(ime, "tehta", teza, "kg")
	
	#oseba[1] bo tukaj ime, oseba[0] bo teža
	print(oseba[1], "tehta", oseba[0], "kg") #Ne delat tako
```


```python
imena = ["Anze", "Blerta", "Marjetka"]
teze = [74, 75, 66]


for oseba in zip(imean, teze):
	print(ime, "tehta", teza, "kg")
```