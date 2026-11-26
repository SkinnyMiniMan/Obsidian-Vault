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
	return not [x in range]
```