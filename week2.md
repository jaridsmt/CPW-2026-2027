LaTeX-oefeningen Week 2 - deel 1
===

### Algemene aandachtspunten

(Zie ook aandachtspunten [vorige les](week1.md). )

Naast `\chapter`, `\section`, `\subsection`, … voor titels,
bestaat er ook nog `\paragraph`. Dit is de zwakste titelvorm en bij
een aantal klassieke LaTeX-stijlen is het effect ervan minimaal: er is geen nummering,
de titel komt gewoon in de tekst te staan (zelfs zonder erna een nieuwe lijn te nemen), alleen
wordt de tekst niet ingesprongen.

In een eerdere oefening hebben we al gebruik gemaakt van de opdracht`\;` om een 'dikke spatie' te plaatsen
in een formule. Af en toe is het inderdaad nodig om zelf witruimte toe te voegen, maar 
doe dit enkel in wiskundemodus. Je vindt enkele tips in [dit kort overzichtje](https://math-linux.com/latex-26/faq/latex-faq/article/latex-horizontal-space-qquad-hspace-thinspace-enspace).

De twee belangrijkste manieren om 'opsomlijsten' te zetten in LaTeX, zijn 
de `itemize`-omgeving, voor een ongenummerde lijst
> * Eerste gedeelte
> * Tweede gedeelte
> * enz.,

en de `enumerate`-omgeving, voor een genummerde lijst, zoals
> 1. Eerste gedeelte
> 2. Tweede gedeelte
> 3. enz.

Hoe die lijst precies genummerd wordt, hangt af van de gebruikte LaTeX-stijl, en kan je ook zelf aanpassen. Een uitstekende package hiervoor is `enumitem`.
Vaak voorkomende stijlen zijn
> (1) Eerste gedeelte  
> (2) Tweede gedeelte  
> (3) enz.,

en ook
> (i) Eerste gedeelte  
> (ii) Tweede gedeelte  
> (iii) enz.,

duikt heel vaak op. Deze laatste stijl kan je bv. genereren door volgende code in je preamble te plaatsen:

```
\usepackage[shortlabels]{enumitem}
    \setenumerate[0]{label={\rm (\roman*)}, leftmargin=*}
```

In een wiskundeartikel wil je soms verwijzen naar een formule die eerder in de tekst
voorkomt. Traditioneel doe je dit door de formules te nummeren met ronde 
haakjes (zoals in 'als we (2) en (17) combineren, bekomen we …'). In LaTeX gebruik 
je hiervoor het volgende:
* Je plaatst de formule in een `equation`-omgeving, in plaats van `\[…\]`
* Je voegt bovenaan, net na `\begin{equation}`, een `\label`-opdracht toe. Daarmee geef je de formule 
een naam waar je later naar kunt verwijzen.
* Om later naar die formule te verwijzen, gebruik je een `\eqref`-opdracht. Deze opdracht zet zelf
de ronde haakjes. (Er bestaat ook een `\ref`-opdracht, maar die dient om naar
hoofdstukken, tabellen, … te verwijzen.)

Bekijk het [voorbeeld uit de inleidingsles](voorbeeld.tex) voor meer details.
     
### Oefeningen

Oefening 4: [Verwacht eindresultaat](latex-oef4.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef4.tex).

* Op enkele plaatsen wordt een `\paragraph`-titel gebruikt. Die zijn te herkennen
aan een nieuwe alinea die niet inspringt en waarvan de eerste 'zin'
niet volledig is ('Voorbeeld.', 'Afleiding van de wortelformule.', …)
* Tip: de oplossing bevat precies één `enumerate`-omgeving.
* De formules in paragraaf §1.1 bevatten toegevoegde witruimte. Tip: deze ruimte is '2em' breed en kan worden toegevoegd
met één enkele LaTeX-opdracht van 5 letters (schuine streep niet meegerekend).

Oefening 5: [Verwacht eindresultaat](latex-oef5.pdf) (PDF) | Vertrek van dit [LaTeX-bestand](latex-oef5.tex).

* Voor de grote Σ waarmee sommen worden aangeduid, gebruik je `\sum`. Wat er boven en onder
deze som staat, noteer je alsof het super- en subscripts zijn.
* Een dubbele verticale streep (voor de *norm* van een vector) noteer je als `\|`
en niet als `||`.
* De term '17<sup>e</sup>' in 17<sup>e</sup> eeuw is geen wiskundige formule. Gebruik `\textsuperscript` voor de e.

[(Wordt vervolgd...)](week2-2.md)
