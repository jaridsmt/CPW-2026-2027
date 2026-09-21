LaTeX-oefeningen Week 3
===

### Algemene aandachtspunten

Om de verzamelingen aan te duiden van natuurlijke, gehele, rationale, reële en complexe getallen
gebruikt men in gedrukte wiskunde teksten hetzij een vet lettertype (**N**, **Z**, **Q**, **R** en **C**),
hetzij het zogenaamde *blackboard bold* (ℕ, ℤ, ℚ, ℝ en ℂ).

Omdat die tekens in wiskundemodus worden gezet, doe je dit 
niet met `\textbf{..}` maar met `\mathbf{..}` voor het vette lettertype, en met `\mathbb{..}` voor het blackboard lettertype.
LaTeX ondersteunt ook nog andere [lettertypes voor wiskundemodus](https://www.overleaf.com/learn/latex/Mathematical_fonts) waarvan
je er in deze oefeningen enkele zult nodig hebben.

### Oefeningen

Oefening 7: [Verwacht eindresultaat](latex-oef7.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef7.tex).

* Het woord 'integraal-' in de eerste alinea kan door LaTeX niet zonder hulp
worden gesplitst (omdat het op een streepje eindigt). Gebruik `\-` om mogelijke
splitsingsplaatsen aan te duiden, of gebruik het commando `\hyphenation{..}` in de preamble.

* De 'script L' waarmee de Laplacetransformatie wordt aangeduid, is een hoofdletter
L gezet in een speciaal lettertype (in wiskundemodus).

* Opgelet! De integralen in deze tekst hebben een 'rechte' d
(ander lettertype in wiskundemodus) voorafgegaan door een dunne spatie. 
Deze manier van noteren lijkt vastgelegd te zijn in 
[een ISO-standaard](https://nhigham.com/2016/01/28/typesetting-mathematics-according-to-the-iso-standard/). 
Het vraagt veel tikwerk om dit correct te doen, maar later zullen we 
daar een oplossing voor vinden.

* Vorige week hebben we een grote accolade naast een stelsel geplaatst met 
een combinatie van `\left\{` en `\right.`. Voor de formule in 
§1.2 gebruik je beter een `cases`-omgeving<sup>1</sup>. Zoals de naam al
aangeeft dient deze omgeving om verschillende *gevallen* op te sommen. 

* De tekst bevat opnieuw een aantal `\paragraph`-opdrachten zoals in 
een aantal oefeningen uit [week 2](week2.md).

* De twee formules helemaal onderaan de bladzijde hebben gelijkheidstekens die
perfect boven elkaar staan. Je kan dit doen met behulp van `\intertext`: de twee
formules bevinden zich in dezelfde `align*`-omgeving<sup>1</sup>, maar die wordt
onderbroken door een gewone tekstlijn.

Oefening 8: [Verwacht eindresultaat](latex-oef8.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef8.tex).

* Deze tekst ziet er wat moderner en 'luchtiger' uit dan de vorige. Dat is
omdat we hier een andere LaTeX-stijl gebruiken, zoals je kan zien in de eerste
lijn van de broncode. Oefening 7 gebruikt de stijl `amsart` en oefening 8
gebruikt `scrartcl`.
* De grote accolades zijn dit keer *niet* een voorbeeld van een `cases`-omgeving.
* Het stelsel in §2 bestaat uit 9 kolommen waarin elk
element gecentreerd is. Dit lukt niet meer met een `align*`-omgeving. Hiervoor
heb je een `array` nodig. 

  Schrijf echter niet zomaar `\begin{array}..\end{array}` waar je anders
`\begin{align*}..\end{align*}` had geschreven - de `array`-omgeving is iets ingewikkelder
maar biedt ook meer opties.
* Je zal ook moeten opzoeken hoe je drie verticale puntjes plaatst - en later ook drie diagonale puntjes.
* Voor de verticale streep in \[A | b\] 
kan je niet zomaar een '|' gebruiken in de broncode. Je vindt de oplossing ergens bij de 
algemene lijst met [LaTeX-aandachtspunten](aandachtspunten.md).  

Oefening 9: [Verwacht eindresultaat](latex-oef9.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef9.tex).

* De titels op deze bladzijde zijn *sections* en *subsections*, maar dan zonder automatische nummering.
* De vier formules bij 'Eigenschappen' hebben hun gelijkheidstekens netjes onder elkaar (zie oefening 7).
* Deze vier formules zijn ook automatisch genummerd!
* Er bestaat een afzonderlijke LaTeX-opdracht voor een drievoudig integraalteken - met een betere spatiëring
dan drie afzonderlijke integraaltekens.
* Om de verticale strepen in de formules in het tweede deel van de tekst
iets langer te maken, gebruik je `\big`, `\Big`, `\bigg` of `\Bigg`. We gebruiken
hier geen `\left|` of `\right|` omdat de strepen hier geen 'haken' voorstellen. In de meeste
gevallen hebben combinaties van `\left` en `\right` echter de voorkeur. 

---

#### Voetnoten

<sup>1</sup> Misschien nog eens herhalen dat we met 'omgeving' een `\begin`-`\end`-combinatie
bedoelen. Dus: `cases`-omgeving = `\begin{cases} .. \end{cases}` (liefst 
gespreid over meerdere lijnen in de broncode).
