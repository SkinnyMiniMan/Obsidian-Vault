<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 2">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 4">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>


`{python icon} (x + 2) // 3` C-jevska rešitev, ne delaj tega
`{python icon} type()`Vrne tip spremenljivke

```python
najm_y = None  
for x0, y0 in ovire:  
    if x0 == x:  
        if najm_y == None or y0 < najm_y:  
            najm_y = y0
```

```python
for x in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]:
	print(x)
```
fuck off range, jaz bom pisal samo še sezname števil

```run-python
print(list(range(22,26)))
```
izpiše prvega, ne izpiše 26, zadnjega iz rangea
če je spodnja meja 0 jo lahko izpustimo
tretji argument v rangeu je korak (npr. vsako drugo, vsako tretje, korak -1(šteje dol)...)

list  --  seznam
array -- tabela
table
to ni isto
v seznamu gre lahko le z zanko do stotega elementa in ga prebere
tabeli lahko rečemo kateri element po vrsti želimo (n-ti element) ter ga izpiše

seznam - sekvenca stvari
tabela - naslavljanje - tabela[ ]

len() pove dolžino seznama če damo 
`{python icon}seznam[len(seznama)]` - > nigga
`{python icon}seznam[len(seznama)-1]` - > jegga

```python
   -7      -6       -5        -4     -3     -2        -1
   1       2        3         4      5       6         7
['Ana', 'Berta', 'Cilka',  'Dani', 'Ema', 'Fanči', 'Greta']
```
isto deluje tudi za terke
`{python icon}seznam[len(seznama)-1]`  == `{python icon}seznam[-1]` 
`{python icon}seznam[len(seznama) // 2]` -> vrne srednji element, vedno uporabljaj //, dela dobro z liho število, ker dejansko obstaja sredina, če je soda ti vrže tretji/četrti element
indeks seznama je vedno celo število
indeks stringa je string

od druge do pete črke:
`{python icon} ime[2:5]` -> črke 2, 3, 4 -> usklajeno z rangeom
`{python icon} ime[2:8:2]` -> črke 2, 3, 6 -> usklajeno z rangeom (vsaka druga med 2 in 8)
`{python icon} ime[3:len(ime)]` -> izpusti prve tri črke (črke 0, 1, 2)
`{python icon} ime[:3]` == `{python icon} ime[0:3]` -> vse do tretje
`{python icon} ime[3:]` -> od tretje do konca
`{python icon} ime[-3:]` -> zadnje tri črke
`{python icon} ime[:-3]` -> vse do zgornje tretje (ki ni -3)
`{python icon} ime[2:-2]` -> odseka prva 2 in zadnje 3
`{python icon} ime[::2]` -> vsak drugi
`{python icon} ime[1::2]` -> vsak drugi (začne drugi)

sezname lahko spreminjam, nizov in terk ne morem spreminjat
LAHKO: spremenimo celoten niz (string)
NE MOREM: spremenit le črke v njem
isto za terke
isto velja za INTe, če ga spremenimo v bistvu naredimo nov objekt ki ima vrednost na katero jo želimo spremeniti, izgubimo pa prejšnjo vrednost (še vedno je shranjena, ampak ni več pisana na x)

`{python icon} imena[2:2] = ["Benjamin"]` -> vrineš na drugo mesto to ime in ostala zamakne
`{python icon} del imena[:2]` -> pobriše prvi dve imeni 

pazi!! `{python icon} imena[2:3] = "Benjamin"
To vrine vse elemente Benjamina , torej vse črke
za dodajanje ne uporabljaj + ker se ti bo dogajala zgornja stvar, uporabljaj:
`{python icon} imena.append("Klara")`

"rečejo kolegi z C-jevskim pogledom na svet"

`{python icon} enumerate()`-> vrne tabelo terk z (indeks, vrednost)

```python
for i, ovira in enumerate(ovire):
	x1, x2, y = ovira
	if x2 - x1 > 3:
		ovire[i] = (x1, x2 +3, y)
	
#ALI 

for i, (x1, x2, y) in enumerate(ovire):
	if x2 - x1 > 3:
		ovire[i] = (x1, x2 +3, y)
```

```python
punce = ["Ana", "Berta", "Cilka"]
fantje = ["Anže", "Beno", "Cene"]
for punca, fant in zip(punce, fantje):
	print(punca, "je plesala z", fant)
	
for i, punca in enumerate(punce)
	print(punca, "je poklicala", punce[i + 1]) ##ta repitev ni lih OK
	
for punca_a, punca_b in zip(punce, punce[1:0]):
	print(punca_a, "je poklicala", punca_b) ##tole dela
	
for punca_a, punca_b in zip(punce[::2], punce[1::2]):
	print(punca_a, "je šla na sprehod z", punca_b)
```

`{python icon}from itertools import pairwise, batched` -> če ne želimo uporabiti zip, funkcije v novih pythonih