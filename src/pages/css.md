---
title: "Kas ir CSS?"
description: "Ieskats stila valodā, kas mājaslapām piešķir izskatu."
---

## Ievads

CSS (Cascading style sheets) atbild par mājas lapu izskatu un izkārtojumu. Bez CSS mājaslapas izskatītos apmēram tā, kā Microsoft Word dokumenti.
Ikvienam HTML elementam var norādīt vienu vai vairākas **klases** un vienu **ID** atribūtu, ko pēc tam var izmantot, rakstot CSS stilus:

```html
<div class="call-to-action" id="cta-text">Sāc programmēt jau <span>šodien!</span></div>
```

CSS stilus paraksti raksta atsevišķos **.css** failos, taču tos var ievietot arī pašā **index.html**, ietverot tos `<style>` tagā:

```html
<style>
  .call-to-action {
    color: yellow;
    text-decoration: underline;
  }

  h1 {
    color: green;
  }

  #cta-text {
    color: blue;
  }

  .call-to-action span {
    color: red;
  }
</style>
```

## Selektori

CSS tiek norādīti _selektori_ jeb atlasītājs, ar punktu `.` priekšā apzīmējot HTML klases un ar `#` — elementa ID atribūtu.

Biežāk pieļautā kļūda, rakstot CSS kodu, ir attiecībā uz _selector specificity_ — ne visi selektori ir "vienlīdz stipri" un viens CSS selektors var pārrakstīt kādu citu.

Augstāk minētā koda rezultāts būs tāds, ka no `.call-to-action` tiks iegūti pirmie stili (nolasīšana notiek secīgi) — teksta pasvītrojums un dzeltenā krāsa. `h1` tags mūsu piemērā nepastāv, tāpēc šīs izmaiņas neredzēsim. `#cta-text` selektors ir ar lielāku _specifiskumu_ nekā `.call-to-action`, tāpēc teksta krāsa mainīsies uz zilu, un, visbeidzot, teksts "šodien!" tiks iekrāsots sarkans, jo tā CSS selektors ir visspecifiskākais — tas vispirms norāda vecākelementu `<div>` ar klasi `call-to-action` un tad tā bērnelementu `<span>`.

Rezultāts:

<style>
  .call-to-action {
    color: yellow;
    text-decoration: underline;
  }

  #cta-text {
    color: blue;
  }

  .call-to-action span {
    color: red;
  }
</style>

<div class="tdbc-card">
<div class="call-to-action" id="cta-text">
	Sāc programmēt jau <span>šodien!</span>
</div>
</div>

## Resursi

[CSS Crash Course For Absolute Beginners](https://www.youtube.com/watch?v=yfoY53QXEnI)

[W3Schools – CSS Tutorial](https://www.w3schools.com/css/)
