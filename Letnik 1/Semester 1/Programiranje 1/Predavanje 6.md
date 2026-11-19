<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 4">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 6">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

```python
def func(x, y, *args)
	print(x, y, args)
	
func(5, 6, 7, "abc", True)
```
To deluje, * -> naredi terko iz preostalih argumentov, če so samo 2 argumenta vrne prazno terko
Lahko tudi:
```python
def func(x, y, z, w)
	print(x+y+z+w)

t = (5, 6, 7, 8)
func(t) #ne dela, x postane cela terka t
func(*t) #dela, razpakira terko

t = (5, 6)
u = (7, 8)
func(*t, *u) #tudi dela
```
paziti moramo na pravilno število elementov
```python
t = (4, 5, 6, 7, 8)
prvi, *_, zadnji = t #dobis prvega in zadnjega
a, b, *u, c = t #u je vse med b in (6, 7)
a, b, c, *u = t #tudi dela
```
100_000_000 = 100000000
lahko ustaviš _ zaradi berljivosti

pyplot -> grafi
npr. pyplot.plot(x, y)

del ni dober (v zanki in brisal prvi element):
	čas narašča po kvadratu dolžine seznama
	ker brišeš prvi element mora prestavit vse elemente za eno mesto v levo
	če brišeš iz konca ni problem

```python
imena = [("Ana", "239705723"), ("Dani", "905678413"), ("Berta", "156852347"), ("Cilka", "658365235")]
def brisi(imena, ime):
	for i, (oseba, ste) in enumerate(imena):
		if oseba == ime:
			del imena[i]
			return
```
To je počasno, zato obstajajo slovarji (dict)
Slovar:
```python
imena = {"Ana": "239705723", "Dani": "905678413", "Berta": "156852347", "Cilka": "658365235"}
imena["Ana"] #Dobis stevilko
"Dani" in imena #True
"Cicilija" in imena #False

#ALI

stevilke = {45: "petinštirideset", 100: "sto"}
f = {print: 45}
f = {True: "res je", False: "ni res"}
```
Lahko so funkcije, številke, logične vrednosti,
Ne morejo biti: nizi
ključ: vrednost
Ključi so lahko:
- int
- float
- bool
- tuple

Vrednost je lahko karkoli
```python
d = {} #prazen slovar
d["Ana"] = "239705723"
```
Vsak ključ lahko nastopa le enkrat, če ta še ne obstaja ga doda, drugače pa ga spremeni




