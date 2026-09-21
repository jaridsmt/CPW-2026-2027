LaTeX-oefeningen Week 4
===

### Algemene aandachtspunten

In LaTeX is het ook mogelijk om je eigen LaTeX-opdracht
te definiëren zodat je knippen en plakken kunt vermijden. Als je bijvoorbeeld
heel veel het symbool voor de natuurlijk getallen nodig hebt, kan
je zelf een opdracht `\N` definiëren die hetzelfde doet als `\mathbf{N}`.

In LaTeX gebruik je hiervoor `\newcommand*`-opdracht<sup>1,2</sup>, of `\renewcommand*` als je een opdracht die al bestaat
een nieuwe betekenis wil geven.

Definities van nieuwe opdrachten plaats je liefst in de *preambule*, t.t.z., vóór de `\begin{document}`.

### Oefeningen

Oefening 10: [Verwacht eindresultaat](latex-oef10.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef10.tex).

* Probeer knippen en plakken te vermijden. Definieer daarom een nieuwe opdracht
`\d` waarmee je de 'd' van een integraal met juiste spatiëring en lettertype kunt zetten.
* Introduceer ook een nieuwe opdracht `\fxdx` als afkorting voor 
de volledige 'f(x) dx' die regelmatig voorkomt. Merk op dat je in de definitie van `\fxdx` gerust de eerder geïntroduceerde
`\d` mag gebruiken. 
* Vergeet de voetnoot niet in deze tekst
* In §1.3 staan de grenzen boven en onder het integraalteken in plaats van ernaast.
Zoek zelf uit hoe je dit doet in LaTeX.
* De allerlaatste limiet heeft twee verschillende subscripts. Gebruik hiervoor `\substack`.

Oefening 11: [Verwacht eindresultaat](latex-oef11.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef11.tex).

**Opmerking** Dit is een zeer uitgebreide oefening. Volg daarom onderstaand
stappenplan (telkens met bijkomende uitleg).

1. Introduceer de afkortingen `\x`, `\y`, `\R`, `\K`, `\C` en `\D` 
voor 'vette' x en y, 'ronde' D en 'schoolbordvette' R, K en C.

2. Voeg de nodige `\chapter`-, `\section`- en `\subsection`-opdrachten in en
zorg voor de *inhoudstafel*. Je moet de inhoudstafel niet zelf maken, LaTeX kan dit voor jou doen. 
(Zoek zelf op hoe je dit voor elkaar krijgt.) De inhoudstafel moet niet alleen worden aangemaakt, je moet ook aan LaTeX vertellen
waar je in je document ergens die inhoudstafel wil zien verschijnen.

3. Vervolledig de stellingen, oefeningen, voorbeelden, …, kortom alles wat eruit ziet als een hoofding
van een stelling.

    Stellingen, gevolgen, definities, e.d., worden op een bijzondere manier 
    aangegeven in LaTeX. (Zoek informatie over `\newtheorem`.) Om aan te 
    duiden waar je deze bijzondere opdrachten moet gebruiken, hebben we Nederlandse 
    terminologie gebruikt, dus *Stelling* i.p.v. *Theorem*,
    *Definitie* i.p.v. *Definition*, enz. 
    
    Zorg ervoor dat je de nummering *exact* reproduceert. Merk bijvoorbeeld het volgende op: 
    * De volgnummers voor *Opmerking* bestaan uit één getal, die voor *Notatie* uit twee getallen, gescheiden
    door een punt, en die voor *Voorbeeld* uit drie getallen.
    * *Stelling*, *Gevolg* en *Propositie* gebruiken dezelfde 'teller': *Gevolg 2.3* komt na *Stelling 2.2* ook al
    is er geen *Gevolg 2.1* of *Gevolg 2.2*. 
    
    Merk op dat de tekst van stellingen e.d. automatisch cursief wordt gezet. Je 
    hoeft er dus niet zelf een `\emph` rond te plaatsen.

4. Vul de inhoud aan van hoofdstuk 2.

5. Zorg voor de bibliografie en de verwijzingen ernaar toe. 
Voor de bibliografie zelf bestaat een aangepaste LaTeX-omgeving, en ook voor
de verwijzingen (Engels: *citations*) is er een speciale LaTeX-opdracht.

6. Vervolledig hoofdstuk 3. Zoals je uit de titels van de paragrafen §3.1 en §3.2
kan afleiden, hebben we hier een toepassing van een `table`- en een `figure`-omgeving, die
o.a. zorgen voor de nummering en de titels van de onderschriften<sup>3</sup>.

   De prent [k3.png](k3.png) wordt gecentreerd afgebeeld op halve grootte. Kijk naar het inleidend [lesvoorbeeld](voorbeeld.tex) om te weten hoe
   je een afbeelding kan invoegen.

7. Doorloop nog eens het volledige document en werk het verder af.   

8. Maak tenslotte de index. (De indexbladzijde tik je niet zelf in, maar kan opnieuw door LaTeX zelf gemaakt worden!) 
   Gebruik hiervoor het
   uitbreidingspakket `imakeidx` (met i) en niet `makeidx` (zonder i). Gebruik hiervoor `\usepackage{…}` in de preambule.

   Je hoeft de index niet volledig na te maken. Je kan je bijvoorbeeld beperken tot 
   de trefwoorden die met een T of een V beginnen.

---

#### Voetnoten

<sup>1</sup>Het oude TeX gebruikt `\def` om een nieuwe opdrachten aan te maken, en je vindt daarvan
nog vele voorbeelden op het Internet, ook in LaTeX-handleidingen - bijvoorbeeld in de tekst over de ISO-standaard voor 
formules met integralen waar we in week 3 naar hebben verwezen. Gebruik in je eigen broncode steeds `\newcommand*` en nooit `\def`!

<sup>2</sup>Ook `\newcommand` (zonder sterretje) bestaat. Voor onze toepassingen doet die precies hetzelfde als `\newcommand*`, 
maar met een minder goede verwerking van fouten. Gebruik dus steeds de versie *met* sterretje.

<sup>3</sup>Er heerst bij beginners vaak verwarring over wat de
 `table`- en `figure`-omgevingen precies doen. Het is *niet* zo dat je een figuur in een tekst invoegt met een `figure`-omgeving -
dat doe je met `\includegraphics` - en ook *niet* zo dat je een tabel aanmaakt
met een `table`-omgeving - daarvoor gebruik je een `array`- of `tabular`-omgeving.

De `table`- en `figure`-omgevingen zijn zogenaamde [floats](https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions) - stukken tekst die
(meestal) afzonderlijk van de rest van de tekst worden gezet, met een genummerd onderschrift. De onderschriften kunnen eventueel
ook automatisch worden opgenomen in een *List of Figures* of *List of Tables* achteraan een boek of artikel.
 
