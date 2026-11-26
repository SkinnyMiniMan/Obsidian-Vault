<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 6">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 8">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

len(ime) ni isto kot len(set(ime)), ker set ne vsebuje duplikatov (če je ime niz)

če želimo kvadrate nekega lista:
```python
s = [7, 3, 9, 4, 1]
t = [x ** 2 for x in s]
```

`[<izraz> for <ime> in <zaporedje>]`

```python
print(max(imena, key = len))
sum([len(ime) for ime in imena]) / len(imena)

[x[0] for x in podatki]
	[teza for teza,_,_ in podatki]#ta je boljsa, je poimenovano za if pogoje
sum([teza for teza,_,_ in podatki]) / len(imena)

[ime for _, ime, _ in podatki]
[ime for _, ime, je_zenska in podatki if not je_zenska]

[x for x in t if x % 2 == 0] #soda
```

`[<izraz> for <ime> in <zaporedje> if <pogoj>]`

```python
[ime for im in imena if random() > 0.5] #GAMBLING, rabi from random import random

[ime for _, ime in sorted([(random(), ime) for ime in imena])]#če nam ne delajo tipke "s h u f f l e"

[x for x in range(1, n + 1) if n % x == 0]

def delitelji(n):
	return [x for x in range(1, n + 1) if n % x == 0]
	
def prastevilo(n):
	return not [x for x in range (2, n) if n % x == 0]

[x for x in range(2, 40) if prastevlo(x)]

{ime: len(ime) for ime in imena}#slovar

r = (x ** 2 for x in range(1, 100000000000000000000000)) #to ne dela, ksneje razlozi

id_v_index = {par[1]: i for i, par in enumerate(s)}#to nam ustvari dict, kjer je ključ vrednost na drugem mestu s, vrednost pa je index za je vrednost v ustvarjenem dictu

s = "MELODIJA"
t = "DELODAJALEC"
[c1 for c1, c2 in zip(s, t) if c1 == c2]#vrne št istoležnih istih črk, slab način
[c1 == c2 for c1, c2 in zip(s, t)]#vrne list boolov kjer je True istoležna ista črka, če jih naredimo sum() dobimo vsoto (True: 1, False: 0)

e = (3, 7, -1)
f = (1, 5, 2)
r = 0
for ei, fi in zip(e,f):
	r += (ei-fi) ** 2
#če sum() dobimo oddaljenost

all([True, True, True])#Vrne True
all([True, True, False])#Vrne False (vsi morajo bit True)
any([False, False, False])#Vrne False
any([False, True, False])#Vrne True (vsaj en)

#npr. vse št sode
all(x % 2 == 0 for x in t)
#vsaj eno sodo
any(x % 2 == 0 for x in t)
```

```python
#namesto zip(s, s[1:])
for t1, t2 in pairwise(pot)
```