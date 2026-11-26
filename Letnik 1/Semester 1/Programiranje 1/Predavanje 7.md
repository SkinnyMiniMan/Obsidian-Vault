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
sum([teza for teza,_,_ in podatki]) / len(imena)

[ime for _, ime, _ in podatki]
[ime for _, ime, je_zenska in podatki if not je_zenska]

```