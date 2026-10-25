<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 2">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href=#>Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>

Zadnjič: Kako v računalniku, katerega enota za zapis informacij je BIT, zapišemo oz kodiramo cela števila

**1. Nepredznačena - pozicijski zapis**
b<sub>i</sub> = {0, 1}
x = b<sub>n-1</sub> b<sub>n-2</sub> ... b<sub>1</sub> b<sub>0</sub>
Vrednost(x) = SUM b<sub>i</sub> * 2<sup>i</sup>
zgled: x = 10110001
Vrednost(x) = 1 * 2<sup>0</sup> + 0 * 2<sup>1</sup> + 0 * 2<sup>2</sup> + 0 * 2<sup>3</sup> + 1 * 2<sup>4</sup> + 1 * 2<sup>5</sup> + 1 * 2<sup>6</sup> +0 * 2<sup>7</sup> + 0 * 2<sup>8</sup>

**2. predznačena števila**
Poglej prejšnje predavanje


**DVOJIŠKI KOMPLEMENT**
![[Številska krožnica]]

Negativno število dobimo tako:
Velikost po pozicijskem zapisu - ena več od največje možne zapisane vrednosti

ob seštevanju (v rezultatu) upoštevamo samo toliko bitov rezultata kot jih imata vhodni spremenljivki (npr. 110 + 010 = 1000, desnega bita ne upošetevamo -> -2 +2 = 0) (PRENOS/carry)
MOŽEN JE PRELIV (overflow) če rezultat preide čez mejo (npr. 011 + 010 = 101) prestopimo mejo med pozitivnimi in negativnimi števili, če se nam to zgodi pomeni da potrebujemo več bitov za zapis našega števila
PRENOS: pove, da za zapis rezultata potrebujemo en dodaten bit
PRELIV: presopili smo mejo med + in - pri zapisu rezultata

**ŠE EN ZAPIS: ENIŠKI OKMPLEMENT**
(ni uporaben)
najvišji bit je predznak: 0 -> +;   1 -> -
za prenos med pozitivnimi in negativnimi števili pa preprosto invertiramo posamezen bite
011 (+3) -> 100 (-3)
001 (+1) -> 110 (-1)
![[Številska krožnica 2]]
Je popolnoma neuporaben za zapis in računanje ker **ima 2 ničli**
<span style="color:#1c7ed6; font-weight:bold">Omogoča pa prehod iz + zapisa v dvojiškem komplementu v - zapisa v dvojiškem komplementu in obratno:</span>
<span style="color:#1c7ed6; font-weight:bold">- NAJPREJ INVERITRAMO BITE IN PRIŠTEJEMO +1</span>
111 -> 000 -> 001


**ALI ZNAMI ZAPISATI REALNA ŠTEVILA??**

37,59 = 3 * 10<sup>1</sup> + 7 * 10<sup>0</sup> + 5 * 10<sup>-1</sup> + 9 * 10<sup>-2</sup>

isto logiko uporabimo za binarna števila:

1011,00101
1 * 2<sup>2</sup> .....
Ne znamo zapisati vejice

**1.** BODI VEJICA VEDNO NA ISTEM MESTU - <span style="color:#9c36b5">FIKSNA VEJICA (fixed point)</span>
-recimo, postavimo vejico vedno med b<sub>k</sub> in b<sub>k-1</sub>
<span style="color:#9c36b5">Vejica je fiksna med zapisom b<sub>k</sub> in b<sub>k-1</sub></span>
Zgled:
n = 8, k = 3
x = 11011 **,** 001
Velikost(x) = 1 * 2<sup>4</sup> + 1 * 2<sup>3</sup> + 0 * 2<sup>2</sup> + 1 * 2<sup>1</sup> + 1 * 2<sup>0</sup> + 1 * 2<sup>-1</sup> + 1 * 2<sup>-2</sup> 1 * 2<sup>-3</sup>

Velikost(x) = SUM(n-1, i = 0) b<sub>i</sub> * 2<sup>i-k</sup>
k - pozicija vejice

<span style="font-weight:bold; text-decoration:underline">Težave:</span>
a) k = 1, n = 4
101<span style="font-weight:bold; color:#f76707">.</span>1
101<span style="font-weight:bold; color:#f76707">.</span>0
Najmanjša razlikam med dvemi števili je najbolj desen bit za vejico; v našem primeru je to 2<sup>-1</sup> = 0.5
natančnost (ang. precision)
<span style="color:#e0313a">NE MOREMO ZAPISATI VSEH REALNIH ŠTEVIL</span>

b) POPRAVIMO TAKO, DA PREMAKNEMO VEJICO V LEVO TAKO, DA BO k = 3
1<span style="font-weight:bold; color:#f76707">.</span>011
najmanjša razlika med dvemi števili je 2<sup>-3</sup> = 0.125
<span style="color:#e0313a">OPS! IZGUBILI SMO OBSEG!</span> celi del števila je lahko le 1 ali 0

<span style="color:#2f9e44">OČITNO v računalniku ne moremo biti absolutno natančni</span>
<span style="color:#2f9e44">Najmanjša razlika med dvemi števili se imenuje </span><span style="color:#2f9e44; font-weight:bold">"UNIT OF LEAST PREVISION" (ULP)</span>

Recimo, da imamo 3 bite za vejico: potem za vejico lahko predstavimo le te vrednosti
,000 -> ,0
,001 -> ,125
,010 -> ,25
,011 -> ,375
,100 -> ,5
,101 -> ,625
,110 -> ,75
,111 -> ,875

**2.** VEJICA NI FIKSNA = <span style="font-weight:bold; color:#f76707">PLAVAJOČA VEJICA</span>
983 = 98,3 * 10<sup>1</sup> = 9,83 * 10<sup>2</sup> = 0,983 * 10<sup>3</sup> = 98,3 * 10<sup>4</sup> = 9830 * 10<sup>-1</sup> = 98300 * 10<sup>-2</sup>
VEJICO PREMIKAM Z EKSPONENTOM
BAZA PA MI OSTAJA ISTA

V DVOJIŠKEM
1011 = 1011 * 2<sup>0</sup> = 101,1 * 2<sup>1</sup> = 10,11 * 2<sup>2</sup> = 10110 * 2<sup>-1</sup> = 101100 * 2<sup>-2</sup>
TUDI TU VEJICA PREMIKAM Z EKSPONENTOM, BAZA OSTAJA(2) ISTA
IDEJA: <span style="color:#f76707">dajmo števila zapisati z velikostjo in eksponentom; potrebujemo 2 ločeni števili</span>
npr.
10<span style="font-weight:bold; color:#f76707">.</span>101110
10101110<sub>(2)</sub> * 2<sup>110<sub>(2)</sub></sup> 
110<sub>(2)</sub> = -6 -> eksponent
10101110<sub>(2)</sub> -> velikost
"Dolgo let nazaj so Američani napadli Irak, ne niso napadli, rešili so nas, Irak je imel orožja za množično uničenje; no to je bilo olje"
moramo se dogovoriti:
	a) koliko bitov za velikost
	b) koliko bitov za eksponent
	c) kako bodo kodirali velikost in eksponent
Krovna organizacija IEEE je zapisala standard in ga označila <span style="text-decoration:underline">IEEE 754</span>

<span style="font-weight:bold; text-decoration:underline">IEEE 754:</span>
- število v plavajoči vejici lahko zapišemo z 32, 64 ali 128 biti
	- 32 bitov - <span style="background-color:rgba(64, 192, 87, 0.35)">enojna natančnost</span> -> z tem se bomo ukvarjali
	- 64 bitov - dvojna natančnost
	- 128 bitov - četvorna natančnost
	še en detajl
		1001 -> 1001 * 2<sup>0</sup> = 100,1 * 2<sup>1</sup> = 10,01 * 2<sup>2</sup> = 1,001 * 2<sup>3</sup>.....
		v vseh primerih moramo vedeti kje je vejica -> zato se dogovorimo
		1. Pred vejico je vedno samo en bit
		2. ta bit mora biti 1
		1110 -> 1,110 * 2<sup>3</sup>
		0010 -> 1,0 * 2<sup>1</sup>
		0,01101 -> 1,101 * 2<sup>-2</sup>
		vsako število se začne z "1," zato mi tega ni treba pisat -> ni mi treba zapisati cele velikosti le vse bite za vejico -> MANTISA
	32 bitov IEEE 754 zapis: <span style="color:#9c36b5">NORMALIZIRANA ŠTEVILA</span>
	![[32  - bitni zapis float]]
	Velikost = (-1)<sup>P</sup> * 1, m * 2<sup>E-127</sup>
	x = 0 | 10110100 | 1110.....0
	  P         E               m
	Vrednost(x) = 2<sup>0</sup> * 1,1110...0 * 2
		E: 10110100
		128 + (32 + 16 + 4) = 128 + 62 = 180
		= +1 * 1,111 * 2<sup>53</sup>
		= +(2<sup>53</sup> + 2<sup>52</sup> + 2<sup>51</sup> + 2<sup>50</sup>)

Ali je res možno vsa števila zapisati vsa števila tako, da je vedno "1," spredaj?
poskusimo na majhnih številih, kjer za eksponent uporabimo 3 bite
0,00001 = 0,00001 * 2<sup>0</sup>
	= 0,0001* 2<sup>-1</sup>
	= 0,001* 2<sup>-2</sup>
	= 0,01* 2<sup>-3</sup>
	= 0,1* 2<sup>-4</sup>
	= 1,0 * 2<sup>-5</sup>
000 = -3 .... 111 = 4 (zapis z odmikom)
najmanjši eksponent je -3!!!, ne moremo zapisati -5!!!!
0,01 * 2<sup>-3</sup> -> to je največ kar lahko premaknem vejico
Zmenimo se: če so v eksponentu same 0, potem nimamo števil, ki se začnejo z "1,", se začnejo z "0," -> ta števila se imenujejo <span style="color:#9c36b5">DENORMALIZIRANA</span>

