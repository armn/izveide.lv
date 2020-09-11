---
title: "Kas ir HTML?"
description: "Ieskats marķēšanas valodā, kas mājaslapām piešķir saturu."
---

## Ievads

Mājaslapas apmeklētājiem _redzamā daļa_ jeb _front-end_ sastāv no [HTML](/html) (saturs, struktūra), [CSS](/css) (stils, izkārtojums) un [JavaScript](/javascript) (interaktivitāte, funkcionalitāte).

HTML (Hypertext Markup Language) ir visu interneta dokumentu un mājaslapu pamatvaloda, kurā semantiski tiek strukturēts lapas saturs — tas ir, datoriem saprotami aprakstīts, kas mūsu lapā ir kas. Pārlūkprogrammā nospiežot F12 taustiņu (vai arī veicot labo klikšķi jebkur un izvēloties "Pārbaudīt" / "Inspect element"), atvērsies programmētāju labākais draugs — _izstrādātāju rīki_, kuras pirmajā cilnē _Elements_ varēs redzēt jebkuras lapas HTML kodu.

![HTML paraugs](/img/html.png)

## Piemērs

Pieņemsim, ka vēlamies sekojošo tekstu pārvērst HTML kodā un ievietot mūsu personīgajā mājaslapā:

> Dārgie kāzu viesi!
> Priecāsimies, ja būsiet kopā ar mums šo sestdien, 20. jūnijā.
> Līdzi uz kāzām nepieciešams ņemt: balles kurpes, mutautiņu un labu noskaņojumu.
> Dāvanās priecāsimies saņemt papagaiļu barību

Kaut arī teksts ir lasāms, katra no tā daļām ir ar atšķirīgu svarīgumu, attiecīgi būtu forši, ja to varētu arī attēlot. HTML princips ir tāds, ka visu lapas saturu nepieciešams ievietot _tagos_ — speciālas nozīmes vārdos, kas saturu aprakstīs jeb _marķēs_.

Iepriekšminētais teksts, pārveidots HTML kodā, varētu izskatīties šādi:

```html
<article>
  <h1>Dārgie kāzu viesi!</h1>
  <p>
    Priecāsimies, ja būsiet kopā ar mums
    <strong>šo sestdien, 20. jūnijā.</strong>
    <br />
    Līdzi uz kāzām nepieciešams ņemt:
  </p>
  <ul>
    <li>balles kurpes</li>
    <li>mutautiņu</li>
    <li>labu noskaņojumu</li>
  </ul>
  <small>Dāvanās priecāsimies saņemt papagaiļu barību</small>
</article>
```

Ar šīs mājaslapas stiliem tas dotu šādu rezultātu:

<div class="tdbc-card tdbc-my-sm">
<article>
  <h1>Dārgie kāzu viesi!</h1>
  <p>
    Priecāsimies, ja būsiet kopā ar mums
    <strong>šo sestdien, 20. jūnijā.</strong>
    <br />
    Līdzi uz kāzām nepieciešams ņemt:
  </p>
  <ul>
    <li>balles kurpes</li>
    <li>mutautiņu</li>
    <li>labu noskaņojumu</li>
  </ul>
  <small>Dāvanās priecāsimies saņemt papagaiļu barību</small>
</article>
</div>

Ievietojot augstākminēto kodu failā, kas beidzas ar paplašinājumu **.html** un atverot to interneta pārlūkprogrammā, mūsu ielūgums ar pārlūka noklusētajiem stiliem izskatītos šādi:
![HTML paraugs](/img/html2.png)

## Tagi

Kopumā HTML specifikācijā ir aprakstīti ap 100 tagu, no kuriem daudzus tā arī nekad neradīsies vajadzība pielietot, taču būtiski būtu zināt vismaz šos:

`<h1> - <h6>` Virsraksti (heading), `<h1>` ir vislielākais

`<p>` Paragrāfi — apzīmē teksta saturu, teikumus.

`<strong>` Treknraksts

`<a>` Links jeb _enkurs_ (anchor) — klikšķināma saite vai poga, kas ved uz citām lapām

`<ul> & <li>` Saraksti

`<img />` Attēli

`<div>` Lapas bloku/elementu nodalīšana

`<br />` Teksta pārnešana jaunā rindiņā

`<hr />` Horizontāla svītra

`<input />` Ievades lauki

Tagi parasti `<strong>`**ieskauj saturu no abām pusēm**`</strong>`, izņemot dažus, kas ir pašaizveroši un bez satura tajos, kā piemēram `<br />` vai `<hr />`. Visbiežāk pieļautās kļūda, rakstot HTML ir tāda, ka tiek atvērts kāds tags, kas pēcāk netiek aizvērts pareizajā vietā, veidojot nepareizu faila struktūru, piemēram:

```html
<div>
<p> <-- Te tiek atvērts paragrāfa teksts
</div> <-- Te tas netika aizvērts, tā vietā aizverot div vecākelementu
</p>
```

Kaut arī pārplūkprogrammas bieži vien sapratīs arī nepareizi strukturētu kodu un _kaut kā to attēlos_, vienmēr vajadzētu pievērst uzmanību tam, vai viss, kas bija jāaizver, ir aizvērts.

Papildu katram no tagiem var norādīt dažādus _atribūtus_, piemēram: `<img>` tagam būs jānorāda `src` parametrs ar adresi uz attēla failu, attiecīgi bildes ievietošana izskatītos šādi:

`<img src="attels.png" />`

## Resursi

[HTML Crash Course For Absolute Beginners](https://www.youtube.com/watch?v=UB1O30fR-EE)

[W3Schools – HTML Tutorial](https://www.w3schools.com/html/default.asp)
