---
name: geekboy-charts
description: >
  Použij, když děláš graf, datovou scénu nebo tabulku měření — v Remotionu, na webu
  i ve statické grafice. Obsahuje kódování dat, tvarosloví, barevné řady, osy, popisky
  a markery.
version: 0.9
updated: 2026-07-26
status: rozpracované
---

# GeekBoy — grafy a data

Doplněk k `design.md`, kapitola 15.

> ⚠️ **Není hotové.** Autor identity připravuje kapitolu *Práce s grafikou* — kompletní
> návody na tvorbu grafů, kombinace barev a řezů včetně ukázek, jak to nedělat.
> Až přijde, tenhle soubor se podle ní srovná; co si tady odporuje, ustoupí.
>
> Do té doby platí, co je níž. Vzniklo to z hotových výstupů, ne z teorie.

---

## 1. Nejdřív geometrie, potom komponenta

Než sáhneš po typu grafu, rozhodni, **jaká vizuální proměnná nese sdělení**:

| Co ukazuješ | Vizuální proměnná |
|---|---|
| velikost a pořadí | délka na společné škále |
| vývoj v čase | vodorovné pořadí a poloha |
| podíl na celku | proporce |
| práh, limit, rezerva | vzdálenost od hranice |
| závislost dvou veličin | poloha ve dvou osách |
| kvalitativní alternativy | zarovnané řádky, ne graf |

**Nesahej po sloupcích jen proto, že existují čísla.** Tabulka je lepší, když jde
o přesné vyhledání hodnoty. Jedna věta je lepší, když jde o jeden závěr.
Graf má smysl tam, kde je vztah vidět rychleji, než by se přečetl.

Pravidlo z `design.md` platí i tady: zjednodušit smíš, zkreslit ne. Když vynecháš řadu
nebo zúžíš rozsah, napiš to k tomu.

---

## 2. Tvarosloví

### Bary jsou rovné

**Sloupce a pruhy nezaobluj.** Ostré hrany působí nadčasově — zaoblené konce barů jsou
móda, která zestárne, a navíc opticky zkracují délku, tedy tu jedinou věc, kterou bar
kóduje.

To platí pro spojitou výplň: sloupce, vodorovné pruhy, výplň score baru, koláč i prstenec.

### Kde zaoblení naopak patří

Zaoblený čtvereček — signaturní tvar značky — se v grafu objevuje na třech místech:

| Prvek | Provedení |
|---|---|
| **koncový bod datové křivky** | zaoblený čtvereček místo `<circle>` |
| **klíč v legendě** | zaoblený čtvereček místo tečky nebo čárky |
| **odrážka u popisků a seznamů** | zaoblený čtvereček |

**Výchozí barva je brand `#1148E6`.** V barevně kódovaném grafu ale marker **nese barvu
své řady** — jinak by nešlo poznat, ke které křivce patří.

Zaoblení podle velikosti prvku, jak popisuje `design.md` kapitola 3: drobné markery
kreslíme jako **squircle**, větší datové čtverečky mají rádius zhruba **11 % strany**.

Do téhle kategorie patří i **segmentové „LED" bary** — pruh složený z jednotlivých
čtverečků. Tam se zaoblují samotné segmenty (11 % strany), protože to nejsou bary,
ale datové čtverečky. Spojitý bar zůstává rovný.

### Rámečky kolem grafů

Graf nemusí být v kartě. Když plocha grafu potřebuje odlišit od pozadí, stačí jemně
odlišený podklad — ne rámeček plus stín plus zaoblení. Tmavý zaoblený obdélník kolem
každého grafu je jeden z reflexů ze seznamu *Takhle to nedělej*.

---

## 3. Barvy

### Kdy stavové a kdy neutrální

**Stavové barvy** — zelená, oranžová, červená — použij, když hodnota **nese stav**:
prošlo / na hraně / neprošlo, ověřeno / neověřeno, v limitu / mimo limit.

**Modrou nebo neutrální škálu** použij, když jde jen o velikost. Delší sloupec není
„success" — je jen delší. Barvit ho zeleně proto, že je příznivý, je záměna měření
za názor.

### Barevné řady

Při více řadách v jednom grafu:

1. **Hlavní řada** — brand modrá `#1148E6`, nebo Blue 40 `#3873FF` na tmavém pozadí.
2. **Porovnávaná řada** — neutrální šedá z antracitové škály (Gray 40 až Gray 60).
3. **Třetí a další** — světlejší kroky modré (Blue 30, Blue 20), ne nové odstíny.

**Testovaný produkt má vždy brand barvu, konkurence je šedá.** Je to čitelné na první
pohled a nevzniká otázka, co která barva znamená.

Stavové barvy do řad nemíchej — ty označují stav, ne identitu řady.

### Význam nikdy jen barvou

Doplň tvarem, popiskem nebo ikonou, ať graf funguje i černobíle a pro barvoslepé.
U dvou řad to řeší přímý popisek u křivky, u sloupců hodnota nad sloupcem.

---

## 4. Osy a škály

- **Nulová základna** u všeho, co kóduje délkou — sloupce, pruhy, plochy. Bez výjimky.
- **Zúžený rozsah** je v pořádku u os, kde délka nic nekóduje (spojnicový graf teplot,
  napětí), ale **musí být viditelně označený** — popiskem osy nebo poznámkou.
- **Nepřehánět rozdíly.** Když je rozdíl mezi produkty 3 %, má vypadat jako 3 %.
- **Mřížka je podklad, ne obsah** — tenká, tlumená, nikdy výraznější než data.
- **Jednotky patří k hodnotám**, ne jen do titulku. Divák často vidí jen výřez.
- U měření uveď **podmínky** — teplota prostředí, verze firmwaru, doba zátěže.

---

## 5. Popisky a čísla

- **Přímý popisek místo legendy**, kdykoli to jde. Legenda nutí oči skákat sem a tam.
- Když legenda být musí, klíč je zaoblený čtvereček v barvě řady.
- **Nechej popiskům místo.** Žádná křivka, čára ani anotace nesmí procházet přes text.
- **Tabulková čísla** (`tnum`) všude, kde se hodnoty porovnávají nebo animují —
  jinak čísla poskakují.
- **Stejná přesnost u rovnocenných hodnot.** Nepiš 3,5 a vedle 3,47.
- Hodnota u sloupce je čitelnější než osa. Když se vejde, dej ji tam a osu zjednoduš.
- **Titulek grafu** říká, co je vidět — ne jak se graf jmenuje. „Nabíječka drží
  35 W i po hodině" je lepší než „Graf výkonu v čase".

---

## 6. Typografie v grafech

| Prvek | Řez | Poznámka |
|---|---|---|
| hlavní nadpis grafu | GeekBoy Display 800 | VERZÁLKY |
| popisek pod nadpisem | Regular 400 | tlumená barva |
| hodnoty a čísla | Bold 700 | `tnum` |
| popisky os | Regular 400 | menší, tlumené |
| poznámka a zdroj | Regular 400 | nejmenší, `--muted` |

---

## 7. Animace grafů

Podrobnosti v `motion.md`. Co platí vždy:

- **Pořadí vykreslení:** mřížka a osy → data → popisky a legendy.
- Data **narůstají ve směru osy** — sloupce zdola, křivka zleva doprava.
- Křivka se kreslí, neskáče. Koncový marker dorazí až se křivkou.
- Easing `dataGrowth`. Žádný bounce, žádná rotace při vstupu.
- Po dokreslení **graf drží klid.** Nic nepulzuje ani nedýchá.

---

## 8. Co zatím není vyřešené

- **Typy grafů**, které oficiálně používáme — zatím vznikají ad hoc podle potřeby.
- **Heatmapy a rozptylové grafy** — pravidla pro ně nemáme.
- **Patterny v plochách** — čeká na značkovou sadu textur.
- **Srovnávací tabulky** — vztah mezi tabulkou a grafem u stejných dat.
- Chování grafů **na výšku** pro sociální sítě.
