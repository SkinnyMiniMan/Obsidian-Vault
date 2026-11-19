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
