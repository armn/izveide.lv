---
title: "Kas ir JavaScript?"
description: "Ieskats programmēšanas valodā, kas mājaslapām piešķir dzīvību."
---

## Ievads

Mājaslapu izstrādē JavaScript visbiežāk izmanto lai iegūtu vai nosūtītu datus serverim, kā arī lai mijiedarbotos ar lietotāju — piemēram, lai pogas reaģētu uz klikšķiem. Šādu mijiedarbības piemēru arī apskatīsim piemērā.

## Piemērs

Sāksim ar pavisam vienkāršas HTML struktūras izveidi, kurā būs poga un virsraksta elements.

```html
<button id="poga">Piespied mani</button>
<h1 id="skaits">0</h1>
```

Gan pogai, gan virsrakstam esam piešķīruši ID, lai pēcāk šos elementus varētu referencēt no JavaScript koda. Pievienosim mūsu HTML struktūrai arī nepieciešamo JavaScript kodu, lai uz pogas klikšķa palielinātos virsraksta skaitlis:

```html
<button id="poga">Piespied mani</button>
<h1 id="skaits">0</h1>

<script>
  document.getElementById("poga").onclick = () => {
    document.getElementById("skaits").textContent =
      parseInt(document.getElementById("skaits").textContent) + 1;
  };
</script>
```

## Skaidrojums

`<script>` elementā ievietoto kodu pārlūkprogramma atpazīs kā JavaScript kodu un veiks tā izpildi. Mūsu piemēra kods darbojas šādi:

1. Mēs vēršamies pie dokumenta objekta `document`, kas satur visu ielādēto mājaslapas struktūru.
2. No dokumenta objekta mēs tālāk izsaucam funkciju `getElementById("poga")`, kas mums ļauj piekļūt pogas elementam.
3. Mēs norādam, ka pogas elementa `onclick` atribūts būs mūsu izveidota _bultas_ funkcija (_arrow function_). To varētu rakstīt arī kā `onclick = function() { ... }`, taču pierakstot to kā `() => { ... }` mēs varam nedaudz saīsināt kodu. Jāņem vērā gan tas, ka vecākās pārlūkprogrammās bultas funkcija nedarbosies un nepieciešams izmantot parasto funkciju.
4. Mūsu funkcijā mēs vēršamies pie HTML elementa ar ID **skaits** un norādam atribūta `textContent` (satura) jauno vērtību — tā paša elementa esošo vērtību plus viens. Esošā vērtība ir ieskauta `parseInt` funkcijā, kas teksta vērtību (_string_) pārveido par skaitli, lai ar to varētu veikt matemātiskas darbības — ja tas netiktu darīts, tad pieskaitīšanas vietā mēs pie pogas nospiešanas redzētu vērtību "01" — JavaScript to uzskatītu par tekstu, kam klāt jāpieliek papildu teksts.

Gala rezultātam vajadzētu darboties šādi:

<button id="poga" class="btn" onclick="document.getElementById('skaits').textContent = parseInt(document.getElementById('skaits').textContent) + 1;">Piespied mani</button>

<h1 style="margin: 0;" id="skaits">0</h1>

## Resursi

[JavaScript Crash Course For Beginners](https://www.youtube.com/watch?v=hdI2bqOjy3c)

[W3Schools – JavaScript Tutorial](https://www.w3schools.com/js/)
