Aandachtspunten
===

Bij een *inline* wiskundige omgeving hebben we liefst dat je de 
notatie `\(...\)` gebruikt, maar we doen een oogje dicht bij het 
verouderde `$...$`. Maar voor een  wiskundige omgeving in '*display*' 
schrijf je steeds `\[...\]` en nooit het verouderde `$$...$$`!

Symbolen die een wiskundig object voorstellen, worden altijd in een wiskundige 
omgeving geplaatst. In het Engelse voorbeeld '*a* denotes a number' worden de twee 'a's
op een andere manier gezet! 

'14:00 uur' is geen wiskundige uitdrukking, hoeft dus niet binnen 
`\(...\)`.  
	
`\(...\)`, `\[...\]`, `equation`, `align` vormen zelf een
wiskundige omgeving. `array`, `cases`, `aligned`, `pmatrix`, 
`bmatrix`, …  moeten echter  *binnen* een wiskundige omgeving komen.
	
In de omgevingen `align` en `aligned` komt er meestal juist één 
`&` op elke regel. Heb je meer kolommen die moeten uitgelijnd worden, dan heb je meerdere ampersands nodig.
Onthoud hierbij dat elke `&` wisselt tussen "rechts uitlijnen" en "links uitlijnen".
Een alternatief is de omgeving `alignat`. Hierbij moet je als *verplicht* argument (tussen akkolades dus) het aantal kolommen meegeven, dus bv. `\begin{alignat}{2}`.
	
Voor een gewoon stelsel gebruik je nooit een `cases`-omgeving. 
	
Er is een verschil tussen  het effect van de LaTeX-code `\(x-\)waarden` 
en dat van `\(x\)-waarden`. Een `-` binnen `\(...\)` wordt gezien als 
een minteken en wordt langer afgebeeld dan een koppelteken.  
	
Een vermenigvuldiging wordt aangegeven met `\cdot` (⋅) 
of met `\times` (×). Nooit met het gewone leesteken punt (.).
	
Gebruik bij voorkeur `\dots` i.p.v.\ het verouderde `\cdots` of `\ldots`.
`\dots` is een "slim" commando dat zelf aan de hand van de context beslist welke dots (lage of gecentreerde dots) het meest geschikt zijn.
Als je een vermenigvuldiging nodig hebt, kan je dit zelf aangeven met het commando `\dotsm` (onthoud dat de "m" voor "multiplication" staat).
In tekst-mode kan je in plaats van `\dots` ook `\textellipsis` gebruiken.
	
Spaties in wiskundige omgeving worden genegeerd door LaTeX, in 
`\text` daarentegen niet. Komt er tekst voor binnen bijvoorbeeld 
`\[...\]`, dan plaats je best een spatie voor en na de tekst binnen 
`\text{...}`. Dus beter `\text{ voor alle }` dan
`\text{voor alle}`.

Om dezelfde reden moet je opletten met 'opsommingen' van wiskundige formules in de tekst. In een zinsnede zoals
'de coördinaten *x*, *y*, *z* en *t*' heb je *drie* afzonderlijke formules nodig om de spatiëring na de komma's
correct te krijgen (`\(x\), \(y\), \(z\) en …`). Bij het alternatief `\(x, y, z\) en …` komt er immers geen spatie na de komma.
Overdrijf hier echter niet, niet elke komma hoort een spatie te hebben. Wel correct zijn bijvoorbeeld `\(0 < i,j,k < n\)` en `\(x,y,z\in\mathbf{R}\)`. 
	
Let op: '`voor\(m+1\)punten`' is niet correct, maar 
'`voor \(m+1\) punten`' wel. 
	
Met de opdrachten `\, \: \; \quad \qquad`
kan je (in wiskunde-modus) bijkomende 
witruimte creëren. Maak daar echter spaarzaam gebruik van.
	
Witruimtes inperken doe je met '`\!`'. Dit is een witruimte van 
*negatieve* lengte.
	
Er is een verschil tussen `|` en `\mid`. Een verticale streep 
gebruik je als 'haakje' en komt steeds in paren voor. De opdracht 
`\mid` is een binaire operator: hij staat tussen twee uitdrukkingen 
(en betekent 'is deler van', of  in de logica, 'of'). De witruimte
is in beide gevallen verschillend.
	
Analoog kan je een dubbele punt noteren als ':' maar ook als 
'`\colon`'. De gewone dubbele punt is een binaire operator en
 wordt bijvoorbeeld gebruikt om verhoudingen aan te geven, zoals in 
 'de homogene coördinaten (*x*:*y*:*z*)', of bij een definitie van een verzameling:
 '{*x* ∈ **R**:*x* > 0}'. 
De notatie `\colon` gebruik je in de
definitie van een functievoorschrift<sup>1</sup>: 
'*f* : **R** → **R** : *x* ↦ *x*² + 1'.

Overgaan naar de volgende regel via `\\` doe je enkel binnen de 
omgevingen `align`, `array`, `tabular`. Je gebruikt dit niet 
binnen tekst.

Meestal heb je ook geen `\\` nodig na de laatste rij van een `align`-, `array`- of `tabular`-omgeving. 
Dit genereert bijkomende witruimte die vaak overbodig is. 
	
Een nieuwe alinea bekom je via een witregel in je broncode. Na een 
witregel zal de tekst een beetje inspringen, wil je dit niet, dan plaats je 
op die plek `\noindent`. Indien je nooit wil inspringen na het 
invoegen van een witruimte, kan je in de *preambule* de opdracht 
`\setlength\parindent{0pt}` invoegen. Dan wordt de opdracht
`\noindent` overbodig, vermits de insprong standaard werd ingesteld op 
0pt. (Maar eigenlijk ben je nu al de *stijl* van het document aan het aanpassen, iets waarmee de uitgever misschien niet akkoord zal gaan.) 
	
De combinatie van een punt en een spatie in je broncode wordt 
geïnterpreteerd als het einde van een zin. Daar plaatst LaTeX een 
grotere spatie om zinnen duidelijk te scheiden. Dus wanneer je een 
afkorting zoals t.e.m. wil gebruiken in het midden van een zin, moet je 
aangeven dat de zin niet eindigt. Dit doe je met behulp van een 
`\ ` (backslash spatie) bv.: `t.e.m.\ de finish`. 
Als alternatief kan je ook `\@` gebruiken vóór de punt (men is er nog niet aan uit welke van de twee opties 'de beste' is… )
	
		
Indien je een `\left` begint, vergeet dan niet dat deze *moet* 
gesloten worden met een `\right`. De gebruikte 'haakjessoort' hoeft 
niet dezelfde te zijn. Wil je dat er niets komt i.p.v. één of ander 
haakje, gebruik dan `\left.` of `\right.`.

'Aanhalingstekens' gaan op een andere manier open (`` ` ``) en dicht (`'`).
"Dubbele aanhalingstekens" schrijf je als twee afzonderlijke 
aanhalingstekens en niet als `"`.
	
Gebruik accolades om te groeperen. Vergelijk bijvoorbeeld het effect van
`\sqrt a+b` met dat van `\sqrt{a+b}`. 
	
Plaats zelf geen onnodige koppeltekens in je broncode. LaTeX splitst de 
woorden zelf indien nodig. 
Slaagt LaTeX er niet in om een woord correct te splitsen, plaats dan 
`\-` op de plaatsen waar het woord mag gesplitst worden. 
	
Auteur, titel, datum en dergelijke worden in de *preambule* 
gedefinieerd. Om de titel dan werkelijk te zetten, gebruik je `\maketitle` 
in het document zelf - ergens na `\begin{document}`, meestal vlak erna maar 
dat is niet verplicht.

De gedachtenstreep '—' schrijf je als `---`. In een 'bereik' zoals 
2014-15, schrijf je `--` om de streep iets langer te maken.
Doe dit echter enkel in tekst, niet in een formule.
	
Wanneer je een afbeelding wil invoegen, gebruik dan 
	`\includegraphics` en zorg dat de afbeelding in dezelfde map is 
	opgeslagen als je broncode. 
	
Een gecentreerde afbeelding invoegen doe je in een 
`center`-omgeving. (Niet via `\hfill` en zeker niet via `\[...\]`. 
Binnen een `figure`- of `table`-omgeving mag je ook `\centering` gebruiken.) 

De `figure`-omgeving heeft in wezen niets met afbeeldingen te maken, 
maar is een 'vlottende' figuur met een onderschrift. Heel gelijkaardig hieraan 
is de `table`-omgeving, die dan weer niets met tabellen te maken heeft. 
Het enige verschil tussen beide is de benaming van het onderschrift ('Figuur' of 'Tabel') en de teller 
die gebruikt wordt voor de nummeringen.
	
Opgepast voor de volgorde van `\caption` en `\label` bij 
	een `figure` of `table`. `\label` komt  *na* de 
	`\caption`. 
	
Bij `\section` of `\subsection` komt er (meestal) vanzelf een punt na de titel. Dit 
	punt hoef je dus niet zelf te plaatsen. Als LaTeX zelf 
geen punt zet achter een titel, dan doet zij dat met opzet!	
Titels beginnen trouwens altijd met een hoofdletter.

Vermijd verouderde TeX-opdrachten. Dus niet `\bf` maar `\textbf`, niet `\choose` 
maar `\binom`, niet `\def` maar `\newcommand*` (*met* sterretje), … 

Wanneer je nieuwe opdrachten definieert, vermijd dan `\(…\)` in de opdracht-definitie, want anders zal
je die opdracht enkel alleenstaand kunnen gebruiken, en niet meer als deel van een grotere definitie. Schrijf 
dus *niet* `\newcommand*\C{\(\mathbf{C}\)}` maar wel `\newcommand*\C{\mathbf{C}}`. Toegegeven, dat betekent dat je nu telkens
`\(\C\)` zult moeten schrijven, waar je anders `\C` zou kunnen schrijven, maar straks heb je misschien '*x* ∈ **C**' 
nodig, en dan kan je nu gewoon `\(x\in\C\)` schrijven, terwijl dat met de eerste definitie een fout veroorzaakt.
	
Maak de LaTeX-broncode overzichtelijk voor jezelf. 

---

#### Voetnoten

<sup>1</sup> Je hebt wellicht al gemerkt dat deze tekst niet met LaTeX is gezet. 
We kunnen dus geen subtiele nuances in lengte van witruimte weergeven en ook
bepaalde wiskundige tekens zien er niet precies uit zoals het hoort. Er zijn al heel wat smeekbeden
gericht naar de ontwikkelaars van de software die we hier gebruiken (Github) om ook
LaTeX te ondersteunen, maar tot nog toe zonder effect.  
