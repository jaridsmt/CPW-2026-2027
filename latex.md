De basisbeginselen van LaTeX
===

Hoe werkt LaTeX?
---

**LaTeX** (spreek uit: 'laatech' - de X is een Griekse hoofdletter chi) is de software
die door wiskundigen gebruikt wordt om teksten te produceren die wiskundige formules bevatten: 
boeken, tijdschriftartikelen, presentaties, cursussen, masterproeven, examens, … De kwaliteit die je met LaTeX kan
bekomen is trouwens zo veel beter dan wat je met een gewone tekstverwerker voor elkaar krijgt dat velen
 LaTeX ook 'misbruiken'
voor gewone teksten zonder één enkele formule erin (en niet alleen wiskundigen).

Wat LaTeX onderscheidt van een gewone tekstverwerker zoals Word, en dat maakt het voor
een absolute beginner ook iets moeilijker om ermee te werken, is dat het geen tekst*verwerker* is, maar 
een tekst*zetter* (oorspronkelijk bedoeld voor de drukindustrie toen niet zomaar iedereen een laserprinter
ter beschikking had).

Dit betekent dat je bij het opstellen van een LaTeX-tekst niet 
meteen het eindresultaat 
te zien krijgt (het is niet 'WYSIWYG: *what you see is what you get*'), maar dat
je het eindresultaat door de LaTeX-software (de LaTeX *processor*) moet laten genereren.

* Wat je als auteur intikt, is een LaTeX-*bestand* - je vindt [hier](voorbeeld.tex) een voorbeeld.
Dit bestand is min of meer leesbaar maar staat doorspekt met allerhande vreemde tekens en opdrachten - bijna
alsof het een programma is, of een script. Alle lettertekens in dit bestand hebben hetzelfde 
lettertype, grootte en kleur<sup>1</sup>.
 
  LaTeX-bestanden hebben doorgaans als extensie `.tex`. (TeX was de voorloper van LaTeX.)
* De LaTeX-processor maakt van het LaTeX-bestand een afdrukbare PDF - zoals in dit [voorbeeld](voorbeeld.pdf). Dit bevat
het beoogde eindresultaat van je werk.

Een wiskundetekst schrijven gebeurt dus in twee stappen: je schrijft LaTeX-*broncode* en slaat die op als `.tex`-bestand en
je laat de LaTeX-processor dit omzetten naar een PDF-bestand, dat je dan naziet op fouten.
Er bestaat heel wat moderne software die je helpt om dit proces gemakkelijk te doorlopen, en
bijvoorbeeld de broncode en het eindresultaat naast elkaar op het scherm afbeeldt.
  
Voor dit vak gebruiken we het *cloud*-gebaseerde [Overleaf](overleaf.md), maar er bestaan ook diverse
(gratis) producten waarmee je LaTeX op je laptop kan installeren: tot enkele jaren
geleden gebruikten we [TeXstudio](https://www.texstudio.org/). (Een LaTeX-bestand dat je met het ene programma hebt aangemaakt,
kan evengoed later door een ander LaTeX-programma worden verwerkt.)

Structuur van de broncode
---

De LaTeX-broncode bestaat uit twee delen: een eerste gedeelte, genaamd
de *preambule* (Engels: *preamble*), en de eigenlijke tekst. De eigenlijke tekst bevindt zich
tussen de volgende lijnen:

     \begin{document}
     …
     \end{document}
Alles wat daarvóór komt, is de preambule. In dit vak zullen niet diep ingaan op wat er allemaal
in de preambule kan of hoort te staan. Als je zelf een nieuwe LaTeX-tekst wil 
schrijven, mag je gerust 'onze' preambule letterlijk overnemen.

De LaTeX-broncode bevat een aantal *opdrachten* die aangeven hoe de LaTeX-processor
bepaalde gedeelten van de tekst moet zetten. Zo betekent bijvoorbeeld

    De \textbf{stelling van Pythagoras} is een wiskundige stelling …
    
Dat de woorden 'stelling van Pythogoras' vetjes moeten worden afgedrukt (bf = *bold face*), en 

    \begin{itemize}
    \item Veni
    \item Vidi
    \item Vinci
    \end{itemize}
geeft aan dat we de beroemde woorden van Caesar als een opsommingslijst moeten worden weergegeven, zoals in
> * Veni
> * Vidi 
> * Vinci

Het valt je meteen op dat de achterwaartse schuine streep (\ *backslash*) en de 
accolades { } ((*curly*) *braces*, *curly brackets*)
een heel belangrijke rol spelen in LaTeX, wat vervelend is voor wie een Azerty-toetsenbord
gebruikt (TeX is ontwikkeld door een Amerikaan…).

LaTeX-opdrachten zijn altijd van de vorm `\naam` meestal gevolgd door 
een argument (= datgene waarop de opdracht
van toepassing is) tussen accolades. 

Het tweede fragment hierboven heet een LaTeX-*omgeving* (LaTeX *environment*) en is van de vorm

    \begin{naam}
    …
    \end{naam}
    
Een omgeving verandert het uitzicht van wat er tussen de `\begin`- en `\end`-lijnen staat.

Voor LaTeX is het ook heel belangrijk te weten wat er als gewone tekst moet worden behandeld, en wat
als wiskundige formule: het woord 'en' wordt op een andere manier gezet dan de formule '*e n*', t.t.z. het product
van *e* en *n*. 

Formules komen in 2 vormen:
* **In de tekst** (*inline*), zoals in 'We kunnen cos<sup>2</sup> α vervangen door …', dat in LaTeX
  genoteerd wordt als

      We kunnen \(\cos^{2}\alpha\) vervangen door …

* **Alleenstaand** (*display*), zoals in
  > En uiteindelijk vinden we
  >
  > &nbsp;&nbsp;&nbsp;   cos<sup>2</sup> α + sin<sup>2</sup> α = 1,
  >                                 
  > door toepassing van de definitie.

  Dit ziet er in de LaTeX-broncode uit als

       En uiteindelijk vinden we
       \[
       \cos^{2}\alpha + \sin^{2}\alpha = 1,
       \]                                    
       door toepassing van de definitie.

Voor *inline* wiskunde gebruik je dus ronde 'haken' `\(…\)`<sup>2</sup>, voor *displayed* wiskunde
gebruik je vierkante 'haken' `\[…\]`.
    
In dit voorbeeld zie je dat ook `^` een speciale betekenis heeft, hiermee plaats
je iets in *superscript*. Voor *subscript* gebruikt LaTeX `_`. In de oefeningen zal je
stap voor stap nieuwe LaTeX-opdrachten leren kennen.
    
LaTeX bepaalt zelf schikking en uitzicht
---
Als je het voorbeeld in detail bekijkt, merk je dat de onderverdeling 
van de tekst in afzonderlijke lijnen in de [broncode](voorbeeld.tex) niet 
helemaal overeenkomt met die in het [eindresultaat](voorbeeld.pdf). Hoe je je lijnen opsplitst in het LaTeX-bestand
is niet belangrijk (tenzij je een lijn volledig blanko laat - zie verder), LaTeX probeert
zelf de beste schikking te vinden en is daar heel goed in.

Denk over je tekst na alsof hij is opgesplitst in *alinea's*, niet in afzonderlijke lijnen.
Gebruik een lege lijn in je broncode om aan te geven dat je een 
nieuwe alinea wil beginnen. In het eindresultaat van het voorbeeld kan je de afzonderlijke
alinea's herkennen doordat het begin van een alinea telkens een beetje inspringt.

Vergelijk dit nu even met wat je ziet in [dit alternatief eindresultaat](voorbeeld-alt.pdf).
Dit is duidelijk dezelfde tekst, maar nu staat er witruimte tussen de 
opeenvolgende alinea's, en springen ze niet langer in. En ook de titel van het artikel en de 
titels van de paragrafen tussendoor zien er helemaal anders uit.

Nochtans was er maar een heel kleine verandering nodig om dit alternatieve resultaat te bekomen: we hebben 
een andere *LaTeX-stijl* gekozen in de preambule<sup>3</sup>. Stijlen zijn vooral belangrijk bij artikels 
in wiskundetijdschriften: vele tijdschriften bieden een eigen LaTeX-stijl aan die je moet gebruiken voor 
hun publicaties. Op die manier garanderen ze uniformiteit binnen hetzelfde tijdschrift, 
en een duidelijk onderscheid met de concurrentie.

Het is belangrijk dat je er bewust van bent dat LaTeX zoveel mogelijk zelf 
het uitzicht van het eindresultaat wil bepalen. Begin bijvoorbeeld niet zelf 
titels van paragrafen vetjes te plaatsen, 
in een groter lettertype, al dan niet gecentreerd, maar gebruik een gepaste LaTeX-opdracht om aan te duiden dat
iets een titel is (met een `\section`- of `\subsection`-opdracht zoals in het voorbeeld), daarmee weet LaTeX genoeg, 
en hij zal je titel dan bovendien ook nog automatisch nummeren zodat je zelf de tel niet moet bijhouden.

Een ander voorbeeld is de opdracht `\emph{…}`. Daarmee geef je aan dat je een stuk
tekst wil benadrukken, en de stijl bepaalt wat het resultaat is (meestal betekent dit
dat de tekst cursief wordt gezet, maar er kan ook kleur gebruikt worden, of de tekst kan vetjes
gezet worden). Er bestaat ook een LaTeX-opdracht om een woord rechtstreeks cursief te zetten, maar dat gebruiken we niet.



Daarom beschrijft men LaTeX soms als WYMIWYG: what you *mean* is what you get.
Je vertelt wat je bedoeling is en LaTeX doet de rest.
In de oefeningen komen we hierop nog terug.   

---

#### Voetnoten

<sup>1</sup> De websitesoftware die we gebruiken voor deze pagina's weet wat LaTeX is 
en  gebruikt kleuren om de inhoud wat te structureren. Als je het bestand zou downloaden en bekijken
met een gewone *editor* (zoals notebook in Windows) dan zie je die kleuren niet.  

<sup>2</sup> In plaats van de 'officiële' notatie `\(…\)` voor inline wiskunde
 in LaTeX
zal je in heel veel teksten nog de notatie `$...$` terugvinden die eigenlijk 
bij het oudere TeX thuishoort. Na 35 jaar heeft de nieuwe LaTeX-notatie echter nog steeds nog
niet overal ingang gevonden. Wij zullen ons best doen
om in de voorbeelden de officiële notatie te gebruiken, maar je mag van ons gerust deze dollarnotatie gebruiken als je dat al gewoon bent. Wat echter
*niet* wordt toegelaten, is de notatie `$$...$$` voor losstaande (*displayed*) formules.

<sup>3</sup> Om dit na te bootsen vervang je de eerste lijn van [voorbeeld.tex](voorbeeld.tex) door de volgende twee lijnen

    \documentclass[11pt,a4paper]{scrartcl}
    \parindent0pt\parskip\baselineskip

  
 


 