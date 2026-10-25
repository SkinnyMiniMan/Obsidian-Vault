<div> 
	<div style="float: left;">
		<a class="internal-link" href=#>◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 2">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

**Kaj sploh je računalniška arhitektura?**
Obstajajo problemi za katere ne moremo (matematično) povedati če jih lahko izračunamo

**Računalniška arhitektura** skuša odgovorit na vprašanje:
**Kakšen naj bo stroj, s katerim se da izračunati vse, 'kar je računljivo?'** (Vprašanje iz obdobja pred 2. svetovno vojno)

**Turingov stroj** -> matematični zapis, ne dejanska izvedba -> stroj z neskončnim trakom
Po 2. svetovni vojni: "Ali znamo narediti Turingov stroj?"

**Von Neuman**: predlagal je računalnik, ki je v osnovi Turingov stroj, ampak je prinesel drugačno izvvedbo
Danes so skoraj vsi računalniki V. N. računalniki -> pravimo da imajo Von Neumanovo **arhitekturo.**

Von Neuman je poskušal **odgovoriti na vprašanja:**
- Kako računalnik dobi navodila/ukaze za računanje? **navodila / ukazi (ang. instructions)**
- Kje naj bodo ukazi shranjeni?
- Kako naj bodo ukazi zapisani?
- V kakšnem vrstnem redu naj računalnik jemlje ukaze (od kjer so shranjeni)?
- Kje naj bodo podatki potrebni za računanje? Kako naj računalnik pride do njih? 
	**podatki -> operandi**
- Kako naj bo v ukazih zapisan podatek o lokaciji (mestu kjer so shranjeni) operandov?
- Podatek o lokaciji operandov mora biti del **ukazov**, ker to je vse kar računalnik dobi za izračun
- Kako naj bodo zapisani ukazi in operandi v računalniku razumljivi obliki? **zapisani -> kodirani**
- Kako naj bo računalnik povezan z okolico?
[[Letnik 1/Semester 1/Računalniška arhitektura/Slovarček|Von Neumanov slovarček]]

**Von Neumanova arhitektura** nam odgovarja na vsa zgornja (temeljna) vprašanja
1. Računalnik naj deluje izključno na osnovi ukazov -> računalnik ne sme spreminjati svoje interne zgradbe glede na ukaze (ne spreminjamo računalnika/internega ožičenja med delovanjem)
2. Naj bodo ukazi shranjeni v enem delu računalnika, ki mu rečemo **pomnilnik** (memory)
3. Naj bodo tudi operandi shranjeni v pomnilniku -> **računalnik s shranjenim programom**
4. Ukazi naj bodo shranjeni eden za drugim v zaporedju -> ==🔴**program**==
5. V računalniku potrebujemo nekaj, kar bo na osnovi teh shranjenih ukazov in operandov računalno -> nekaj kar bo **izvajalo** (proccessing) te ukaze in zahtevane oprecije ->**Centralna procesna enota (CPE)** 
6. Kako naj centralna procesna enota ve kje je naslednji ukaz? -> CPE naj ima nekaj, kamor ob zagonu računalnika zapišemo kje se nahaja prvi ukaz, potem pa ker so ukazi shranjeni eden za drugim bo CPE vsakič avtomatsko, ko izvede en ukaz, to "nekaj" povečala za 1 (i++)
   "nekaj" je v bistvu števec (ki se začne z 0), ki nam pove koliko ukazov smo izvedli, hkrati pa kaže na kateri ukaz naj gre naprej -> **programski števec (program counter / PC); PC = ==🔵PC + 1**==; kaže kje je naslednji ukaz -> hrani **naslov** naslednjega ukaza; naslov -> lokacija 
7. Predpostavimo naslednji ukaz: seštej A in B in shrani v C:
   A, B, C -> operandi -> v pomnilniku in ukaz vsebuje le njihove naslove -> zato mora CPE najprej A in B prebrati in pomnilnika, ju hranit pri sebi, nato seštet in rezultat shranit nazaj v pomnilnik v C -> TOREJ: CPE mora imeti neko shrambo, da pri sebi začasno shrani operanda
   -> CPE mora imeti majhen pomnilnik za začasno shranjevanje operandov -> REGISTRI
   seštej -> operacija
8. CPE potrebuje neko enoto ki bo dejansko računala -> izvajala bo aritmetične in logične operacije -> **aritmetično-logična enota ALE**
9. Računalnik mora imeti možnost, da dobi informacijo iz zunanjega sveta in informacijo posreduje v zunanji svet -> **Vhodno-Izhodne enote** (input-output units)
10. Kaj sme centralna procesna enota spreminjat v pomnilniku?
    OPRANDE JA; UKAZOV NE (to je vzel iz modela Turingovega stroja)
[[Von Neumonov model.canvas|Von Neumanov model/shema]]


**Ahmdalov problem**
Ahmdal se je vprašal: Ali je možno z N Von Neumanovih računalnikov nek program Nkrat hitreje izvesti

Če najdemo del programa, ki je neodvisen od ostalega, lahko tisti del pohitrimo z N računalniki
S - speedup
f - del programa ki smo ga pohitrili
N - število Von Neumanovih računalnikov

$$
S(N) = \frac{1}{(\frac{f}{N} + (1-f)}
$$
Zgled:
f = 0.5, N = 1000
S(1000) = \frac{1}{(\frac{0.5}{1000} + (1-0.5)} = \frac{1}{(0.0005 + 0.5} = 1 / 0.5005 = 2

Zgled:
f = 0.9, N = 1000
S(1000) = 1 / 0.1009 = 1/ 0.1 = 10