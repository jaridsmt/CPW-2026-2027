Beamer - presentaties in LaTeX
===
**Beamer** is een LaTeX-pakket voor het maken van presentaties. Als we
ons op voordrachten op conferenties mogen baseren, wordt Beamer gebruikt door de overgrote meerderheid van wiskundigen.

Hieronder geven we een kort overzicht van de belangrijkste elementen van een Beamer-presentatie
aan de hand van deze [slides](beamer-voorbeeld.pdf),
gemaakt met dit [LaTeX-bestand](beamer-voorbeeld.tex).
Bijkomende informatie kan je o.a. vinden 
op de [hulppagina's van Overleaf](https://www.overleaf.com/learn/latex/beamer),
een [tutorial bij Overleaf](https://www.overleaf.com/learn/latex/Beamer_Presentations:_A_Tutorial_for_Beginners_(Part_1)%E2%80%94Getting_Started),
en natuurlijk ook
in de [officiële handleiding](http://ctan.cs.uu.nl/macros/latex/contrib/beamer/doc/beameruserguide.pdf) (242 blz!).

#### De preambule

Een LaTeX-bestand voor een Beamer-presentatie begint met de lijn

    \documentclass{beamer}
Verder in de preambule kan ook een thema en een kleurenschema ingesteld worden<sup>1</sup>.
Je geeft er ook aan wat titel, subtitel, auteur, … zijn van de presentatie.
Deze informatie dient niet enkel voor de titelpagina (zoals bij `\maketitle` 
in een 'gewone' LaTeX-tekst - maar in Beamer heet dit `\titlepage`) maar wordt
ook overgenomen in de voettekst van
elke slide<sup>2</sup>. Als de titel (subtitel, auteur, …) te lang is voor de voettekst,
kan je ook een korter alternatief opgeven tussen *vierkante* haakjes:

    \title[Beamer]{Beamer: presentaties maken met \LaTeX}
Neem voor je eigen presentaties gerust de preambule over 
uit het [Beamer-voorbeeld](beamer-voorbeeld.tex).

#### Opbouw

Slides in Beamer heten *frames*. Elk frame wordt gezet binnen een afzonderlijke `frame`-omgeving.
Er bestaan hiervoor enkele varianten.

1. Een frame met een titel:

       \begin{frame}{Dit is de titel}
       ...
       \end{frame}
2. Een frame met titel en subtitel:

       \begin{frame}{Dit is de titel}{En dit de subtitel}       
3. En een frame zonder titel, en zonder kop- en voetteksten (voor een titelpagina bijvoorbeeld):

       \begin{frame}[plain]

#### Inhoudstafel

Het is gebruikelijk om in het begin van een presentatie een kort overzicht te geven van
de verschillende onderwerpen die je wil bespreken, zoals in slide 4/9 van het voorbeeld.
Vaak wordt dit overzicht ook tussendoor herhaald, waarbij dan het punt
waar de presentatie op dat moment is aanbeland, wordt gemarkeerd (slide 5/9).           

Beamer (her)gebruikt hiervoor de `\section`- en `\subsection`-opdrachten. Je plaats die
*tussen* de frames. In tegenstelling tot bij een gewone LaTeX-tekst, worden
de `\section`- en `\subsection`-titels niet afgedrukt op de plaats waar 
ze zijn opgegeven -
ze staan immers niet binnen een frame - maar worden ze intern geregistreerd zodat Beamer
automatisch een inhoudsopgave kan maken. Dit gebeurt met de opdracht `\tableofcontents`:

    \begin{frame}{Inhoud}
    \tableofcontents
    \end{frame}
Of, als je je huidige plaats in de presentatie wil markeren:

    \tableofcontents[currentsection]
    
Omdat de `\section`- en `\subsection`-titels niet vanzelf worden afgedrukt, moet je
die vaak overnemen als titel van de betreffende frames. Je kan knippen en plakken vermijden
door voor die titels `\secname` of `\subsecname` te gebruiken.
(Zie [broncode](beamer-voorbeeld.tex) van de voorbeeldpresentatie.) 

#### Blokken

Om een stuk tekst in een blok te plaatsen, gebruik je de `block`-omgeving.
    
    \begin{block}{Titel van het blok}
    ...
    \end{block}
Ook een lege titel is toegelaten (`\begin{block}{}`). Voorbeelden en varianten vind je op slide 6/9.
Merk op dat stelling en bewijzen automatisch als blokken worden afgebeeld (slide 7/9).

#### Meerdere kolommen

Je kan een (deel van een) slide in twee (of meerdere) kolommen verdelen
met de `columns`-omgeving (meervoud),
waarbij je dan voor elke afzonderlijke kolom een `column`-omgeving gebruikt (enkelvoud):

    \begin{columns}
       \begin{column}[t]{5cm}
       ...
       \end{column}
       \begin{column}[t]{5cm}
       ...
       \end{column}
    \end{columns}
De `[t]` geeft aan dat beide kolommen bovenaan gealigneerd moeten worden (t = *top*).

#### Overlays

Een *frame* correspondeert niet noodzakelijk met één enkele slide of één enkele pagina
in de PDF die uiteindelijk geproduceerd wordt, het is ook mogelijk om een frame pas
deel na deel te laten verschijnen. (Zoals je al meteen merkt in slide 2/9 van de voorbeeldpresentatie.)

Er zijn in essentie twee manieren om dergelijke *overlays* te bekomen<sup>3</sup>.

Voor eenvoudige overgangen gebruik je `\pause` op de plaatsen in de broncode waar je
een overgang wil naar de volgende slide. Onderstaande lijst wordt bijvoorbeeld in 3 stappen getoond.

    \begin{itemize}
      \item …
    \pause
      \item …
    \pause
      \item …
    \end{itemize}
Voor de meeste toepassingen heb je aan `\pause` genoeg. Wil je echter meer controle over de volgorde
waarin je delen van het frame wil tonen (zoals in slide 9/9), dan kan je *scheve haken* (`<…>`) gebruiken. In dit voorbeeld
wordt de lijst van onder naar boven vrijgegeven:

    \begin{itemize}
      \item<3-> …
      \item<2-> …
      \item<1-> …
    \end{itemize}
De code '`2-`' betekent 'vanaf slide 2 tot het einde'. Er is heel wat mogelijk met deze notatie, maar het zou
ons te ver leiden om hier in detail te treden. Het is bovendien een slecht
idee om daar in een presentatie al te veel gebruik van te maken.     

---

#### Voetnoten

<sup>1</sup> De [standaardschema's](https://deic-web.uab.cat/~iblanes/beamer_gallery/index_by_theme_and_color.html)
zijn nogal saai en herkenbaar, en de vele opties verschillen
eigenlijk maar weinig van elkaar. Blijkbaar willen wiskundigen
de aandacht van de luisteraar niet te veel afleiden van de inhoud van hun presentaties.    

<sup>2</sup> of in de koptekst, of in een zijbalk, afhankelijk van het gekozen thema.

<sup>3</sup> Je kan beide manieren door elkaar gebruiken in dezelfde presentatie, maar *niet* binnen
hetzelfde frame.