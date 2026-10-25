<div> 
	<div style="float: left;">
		<a class="internal-link" href="predavanje 1">◀ Prejšnje predavanje</a>
	</div> 
	<div style="float: right;"> 
		<a class="internal-link" href="predavanje 3">Naslednje predavanje ▶</a> 
	</div> 
	<div style="clear: both;"></div>
</div>


<span style="font-weight:bold; text-decoration:underline">POMNILNIK</span> (Von Noumanov model)

Pomnilnik naj bo zaporedje enako velikih pomnilniških pesed (memory word)

![[Pomnilnik.excalidraw]]
- Naj bo vsaka beseda "ENOLIČNO NASLOVLJENJA"
  Enolično naslovljena -> vsaka beseda ima svoj naslov (indeks) po katerem je ločena od ostalih besed
- Vsaka beseda hrani enako količino informacij
- <span style="background-color:rgba(255, 146, 43, 0.4)">Najmanjša količina informacije v sodobnih računalniških sistemih</span> -> Zaradi izdelave računalnikov lahko v najmanjših gradnikih hranimo informacije napetost 
  ≈0V "NI" "0"
  ali                      najmanjša količina inforamcij, ki ima vrednost bodisi 0 ali 1, to je bit (b)
               b = {0, 1}
  ≈1.1V "JE" "1"

Pomnilniška beseda:
![[Pomnilniška beseda.excalidraw]]

b<sub>0</sub> -> bit z najmanjšo težo (najmanj pomemben bit) Least significant bit (LSB)
b<sub>m-1</sub> ->bit z največjo težo (najbolj pomemben bit) Most significant bit (MSB)
V praksi je najbolj pogost M = 8

Beseda je dolga 8 bitov -> zato je dobil ime BYTE (bajt)
Pomnilnik: N pomnilniških bese dolgih M bitov

Informacija (predstavljena z biti) so razdeljeni na:
- ukazi
- operandi

Kako so ukazi in operandi prikazani z biti??
Začeli bodo z operandi; Operandi so :
- števila
- znaki (znakovni nizi)
- barve
- zvok .....
Vse to je predstavljeno z biti!!!
10010110 - Kaj je to???
-> hudo!!! Pojma nimam!!!
-> iz bitnega zapisa ne povemo pomenu te informacije
-> mi programerji se odločimo kako bomo interpretirali kako se bomo odločali interpretirati vsebino neke pomnilniške besede

omejimo se na: CELA NEPREDZNAČENA ŠTEVILA
-> kako z biti zapišemo (kodiramo) cela nepredznačena števila
-> kako to storimo s števili, ki jih poznamo -> DESETIŠKIMI 743 -> 3 * 10<sup>0</sup> + 4* 10<sup>1</sup> + 7 * 10<sup>2</sup>
-> vrednost števila je določen s postavitvijo posameznih števk -> Pozicijski zapis števil
V splošnem:
x<sub>n-1</sub> x<sub>n-2</sub> ... x<sub>0</sub>
$$
Vrednost = ∑xi * bi
$$

Besedni sistem: B=10, x<sub>i</sub> = {0....9}

V računalniku x<sub>i</sub> = {0, 1}; B = 2 (x<sub>i</sub> = b<sub>i</sub>) -> **Dvojiški sistem**

-> najboljši zapis za zapisovanje celih nepredznačenih števil je pozicijski

računanje iz dvojiškega v desetiški....

"Na univerzi smo, moram se delat pametnega, ni smešno, res je"
"Jaz bi rad da moja banka vedno računa samo z nepredznačenimi števili."
"Žena bi bila jezna ko bi prinesel novo kolo domov"

<span style="text-decoration:underline; font-weight:bold">CELA PREDZNAČENA ŠTEVILA</span>
-> kako bitnemu zapisu dodat predznak (+, -)

**1.** Predznak in velikost
- ful izi: najbolj pomemben bit naj bo predznak:
	- 0 -> +
	- 1 -> -
	0011 -> 0(+) 011(vrednost/velikost določimo z pozicijskim zapisom) = 3 -> +3
	1011 -> -3
	Dajmo sešteti +3 in -3:
		0011 (+3) + 1011 (-3) = 1110 (-6) -> hmmm?? to ni prav!!
		"Ne gremo še domov, ne znamo seštevat"
**2.** Zapis števil z odmikom
- dajmo reči n = 3, da nam bo lažje
- napišemo ta števila na premico
- ![[Predavanje 2 2026-10-15 16.22.35.excalidraw]]
- prvi bit nam pove ali je pozitivno ali negativno: 0 = -; 1 = +
- Kako pa določimo vrednost/velikost v takem pogoju
	- easy: pričakujemo vrednost 'sredine' oddaljen od pozicijske vrednosti števila
- V našem primeru je sredina: 100
- v(110) = 6 - 4 = 2
- v(011) = 3 - 4 = -1
- odmik (offset) je 2<sup>n-1</sup>
	- 0 + (-3) = 100 +001 = 101 (1) -> NAROBE (še vedno ne znam računat)
- <span style="background-color:rgba(64, 192, 87, 0.35)">števila so leksikografsko razvrščena</span>
**3.** **Dvojiški komplement**
- poskusimo s številsko krožnico
- ![[Številska krožnica]]
- Ali znamo izračunati vrednost?
	-  "+" -> pozicijski zapis
	-  "-" -> pozicija - 2<sup>3</sup>
- +3: 011
  -3: 101
  101 + 011 = (1)000 -> 0 -> "Zdaj znamo računa"
  dodatna enica se imenuje prenos (carry) in je ne upoštevamo
- "Kakšen oksimoron sem zdaj povedal; politiki ko nam lažejo, saj nam zmeraj lažejo"
- +2: 010
  -3: 101
  010 + 101 = 111 -> -1
- +3: 011
  +1: 001
  011 + 001 = 100 -> -4 "o fak" ??? -> "kaj pol ne znam računat??"
- prestopili smo "rumeno mejo", ki je ne smemo prestopiti, rezultat se nam je "prelil" v napačen predznak
  rezultat se nam je prelil čez rumeno mejo v napačen predznak
- -2: 110
  -3: 101
  110 + 101 = (1)011 -> +3; spet se mi je rezultat prelil čez mejo predznaka
- **UGOTOVITEV**
	- Če seštevam obratno predznačeni števili bom vedno dobil pravilni rezultat,
	- če pa sešteva dve enako predznačeni števili, se mi lahko zgodi PRELIV
	- Preliv ne pomeni, da ne znamo računat, pomeni le, da imam premalo cifer za zapis rezultata
	- V TEM ZAPISU ZNAM RAČUNAT !!!