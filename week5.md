LaTeX-oefeningen Week 5
===

### Beamer-oefening

Beamer-oefening 1:  [Verwacht eindresultaat](beamer-oef1.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](beamer-oef1.tex).

Dit is een oefening die gebruikt maakt van het [Beamer](beamer.md)-pakket
voor presentaties.

* Je hebt de volgende prenten nodig: [LogoUGent.png](LogoUGent.png) en [fanovlak.png](fanovlak.png)
* Gebruik zelfgedefinieerde LaTeX-opdrachten voor 'rechtopstaande' PG en 'ronde' B.
  Je hebt ook enkele 'theorem'-omgevingen nodig.
* Niet alles op de titelpagina komt uit de preambule: het frame met de titelpagina
  bevat behalve `\titlepage` ook nog bijkomende LaTeX-opdrachten voor het logo.
* Zorg voor correcte voetteksten op elke slide.
* Het logo op de titelpagina heeft een breedte die 25% van de totale tekstbreedte
  bedraagt. Voor de linkerkolom op slide 10 is dit 41% en voor de rechterkolom 56%. Het Fano-vlak op slide 7 wordt afgebeeld op 20% van zijn normale grootte.
* Merk op dat slides 9-11 dezelfde (hoofd)titel hebben, maar dit is niet dezelfde als
  in de automatisch gegenereerde inhoudstafel op slide 8. Om knippen en plakken te vermijden,
  kan je bijvoorbeeld een eigen opdracht `\mysecname` definiëren.
* Op slide 10 staan een aantal formules in een `itemize`-omgeving. Als je die letterlijk overneemt,
  zie je dat ze kleiner worden voorgesteld (en met sub- en superscripts op een andere plaats) dan
  in de PDF - ze worden immers in *text style* gezet, en niet in *display style*. Zoek uit hoe je
  dit kan oplossen.
* Probeer alle overgangen (*overlays*) zo goed mogelijk na te bootsen.
  (Merk bijvoorbeeld de verandering van kleur op bij het woord *geen* in slide 7.)
  Helaas zal `\pause` niet altijd volstaan.
* Als je nieuwe 'theorem'-omgevingen aanmaakt, moet je opletten dat je geen naam gebruikt
  die in LaTeX al is voorgedefinieerd: `theorem`, `definition` en `lemma`
  bestaan bijvoorbeeld al, dus

      \newtheorem{theorem}{Stelling}    % Werkt niet!
  zal een fout geven - en helaas één met een zeer onduidelijke foutboodschap.

  Je mag ook geen naam kiezen die al bestaat als LaTeX-omgeving of -opdracht. Dus ook
  niet `itemize` of `def`. (Kies dus Nederlandse namen of namen met hoofdletters.)
* In de LaTeX-broncode die je cadeau krijgt, staan ook enkele wiskundige formules. Lees die goed
  na, want er kunnen delen ontbreken.

Merk op dat foutboodschappen bij Beamer-teksten meestal pas gerapporteerd
worden op het einde van het frame waarin ze voorkomen. Dit maakt het 'debuggen' van Beamer
een stuk moeilijker dan bij gewone LaTeX.

### Synthese-oefeningen

(Wellicht wat te veel om in een halve les nog voor elkaar te krijgen ...)

Oefening 12: [Verwacht eindresultaat](latex-oef12.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef12.tex).

**Opmerking** Je hoeft het eindresultaat niet volledig na te bootsen - twee rijen per tabel (+ hoofding, als die er is)
zijn voldoende.

* Dit is een oefening op het maken van tabellen. Tabellen waarin de inhoud hoofdzakelijk
  uit wiskunde bestaat (zoals in deze oefening), maak je met de `array`-omgeving.
  Voor tekst-tabellen gebruikt men de `tabular`-omgeving. Dus *niet* een `table`-omgeving.
* Je kan in LaTeX niet alleen zelf nieuwe opdrachten definiëren, of nieuwe 'stellingen', zoals we in
  eerdere oefeningen al hebben gedaan, maar ook nieuwe omgevingen (komt volgende week aan bod)
  en nieuwe 'wiskundige operatoren' zoals `\cos` en `\ln`. In deze
  oefening heb je een `\tg` nodig voor de Nederlandse vorm van de tangens.
* De kolommen in de tabel op de tweede bladzijde staan heel wat verder uit elkaar
  dan gebruikelijk. Ook de rijen staan 40% verder uit elkaar dan normaal.

  Om onduidelijke redenen is de notatie die men gebruikt om de kolomafstand
  te vergroten helemaal anders dan die voor de rijafstand…
* Ook bij de blokmatrices hebben we de rijafstand met 20% vergroot.

Beamer-oefening 2: [Verwacht eindresultaat](beamer-oef2.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](beamer-oef2.tex).

Dit is een 'combinatie'oefening: je zal heel wat Beamer-elementen moeten gebruiken, maar
er zijn ook enkele LaTeX-nieuwigheden in deze oefening.

Je hebt de volgende afbeeldingen nodig: [Dice.jpg](Dice.jpg),
[tetrahedral.png](tetrahedral.png), [octahedral.png](octahedral.png)
en [icosahedral.png](icosahedral.png).

* In de preambule krijg je enkele nieuwe LaTeX-opdrachten cadeau voor enkele
  variabelen in een vet lettertype<sup>1</sup>. We hebben ook het pakket `multirow`
  toegevoegd waarmee je in tabellen een cel over meerdere rijen kan laten lopen.
  Je hebt dit nodig voor slide 8/10.
* Op slide 3/10 hebben we hier en daar extra verticale witruinte toegevoegd - in het 'Afspraak'-blok
  tussen de twee lijnen (medium tussenruimte) en boven de opsomming (grote tussenruimte).
* Let goed op de *overgangen* in de slides, in het bijzonder in slides 3/10 en 4/10.
  Gebruik hiervoor de Beamer-opdrachten`\only<…>` en `\onslide<…>`.
* Vanaf slide 5/10 kan je echter opnieuw gewoon `\pause` gebruiken
* In slide 5/10 geven we expliciet aan dat de tekst in het grijs moet worden gezet.
* In slide 6/10 is de eerste formule in de `align`-omgeving *niet* genummerd, maar de
  andere twee wel.
* Slide 7/10 bestaat uit twee kolommen, éébn van 1,5 cm breed, en één van 8,5 cm.
* In de tabellen op slides 7/10 en 8/10 mag je je gerust beperken tot de hoofding
  en één enkele rij. In slide 8/10 heeft de tabel in de broncode 6 kolommen (niet 5) en 8 rijen (niet 5).
  We hebben de tussenruimte tussen de eerste twee kolommen verkleind tot één enkele spatie.
* Gebruik voor die tabellen dit keer een `tabular`- in plaats van een `array`-omgeving.
* Maak goed gebruik van `\secname` om knippen en plakken van titels te vermijden.
* De commutatieve diagrammen op slides 9/10 en 10/10 zijn gemaakt met `array`-omgevingen<sup>2</sup>.
  De pijlen naar beneden in het *Associativiteit*-blok kan je op
  de volgende manier zetten:

       {\scriptstyle (m,\mathrm{Id})}\!\downarrow
       \downarrow\!{\scriptstyle m}}
  maar omdat je dit soort pijlen meer dan één keer zult nodig hebben, definieer je echter beter
  de opdrachten `\downl` en `\downr` zodat je bovenstaande kunt afkorten tot

       \downl{(m,\mathrm{Id})}
       \downr{m}
  Dit zijn met andere woorden LaTeX-opdrachten met één parameter.

-----

#### Voetnoten

<sup>1</sup> Een [recente bug in beamer](https://tex.stackexchange.com/questions/565069/beamer-bold-math-no-longer-working)
had ervoor gezorgd dat `\mathbf` niet in vetjes
werd gezet, maar enkel rechtop in plaats van cursief. We hebben dit opgelost
met onderstaande lijn in de preambule:

    \DeclareFontShape{OT1}{cmss}{b}{n}{<->ssub * cmss/bx/n}{}

<sup>2</sup> Er bestaan verschillende LaTeX-pakketten waarmee je dergelijke diagrammen kunt
maken, maar voor deze opgave mag je die niet gebruiken.
