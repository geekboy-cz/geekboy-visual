---
name: geekboy-charts
description: >
  Použij, když děláš graf, datovou scénu nebo tabulku měření — v Remotionu, na webu
  i ve statické grafice. Obsahuje kódování dat, tvarosloví, barevné řady, osy, popisky
  a markery.
version: 1.0
updated: 2026-07-27
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
| **klíč v legendě u plošné řady** | zaoblený čtvereček — bary, plochy, buňky, siluety |
| **odrážka u popisků a seznamů** | zaoblený čtvereček |

⚠️ **Klíč u křivky čtvereček není.** Klíč napodobuje tvar toho, co zastupuje — u spojnicové
řady je to **úsečka**, ne čtverec. Podrobnosti a rozměry v kapitole 5.

**Výchozí barva je brand `#1148E6`.** V barevně kódovaném grafu ale marker **nese barvu
své řady** — jinak by nešlo poznat, ke které křivce patří.

Zaoblení podle velikosti prvku, jak popisuje `design.md` kapitola 3: drobné markery
kreslíme jako **squircle**, větší datové čtverečky mají rádius zhruba **11 % strany**.

Do téhle kategorie patří i **segmentové „LED" bary** — pruh složený z jednotlivých
čtverečků. Tam se zaoblují samotné segmenty (11 % strany), protože to nejsou bary,
ale datové čtverečky. Spojitý bar zůstává rovný.

### Plocha grafu

**Na webu a v aplikacích graf stojí na vlastní ploše.** Stránka recenze střídá odstavce,
tabulky, fotky a grafy — bez vymezení graf splyne s textem a čtenář nepozná, kde začínají
data. Plocha je funkční předěl, ne dekorace.

| Vrstva | Hodnota |
|---|---|
| podklad | `--chart-bg` — v dark Gray 100, v light bílá |
| rámeček | 1 px `--chart-border` — v dark Gray 90, v light Gray 20 |
| zaoblení | 16 px |
| vnitřní okraj | ~34 px svisle, `clamp(22px, 3.5vw, 40px)` vodorovně |

Zaoblení 16 px je **vědomá výjimka z tabulky zaoblení** v `design.md` kapitole 9
(karty 12 px) — plocha grafu je větší než karta a při 12 px působí těsně. Nic jiného
na stránce 16 px nemá.

**Co pořád platí:** ne rámeček plus stín plus zaoblení najednou — podklad a linka, tím to
končí. A **karta uvnitř plochy grafu už je karta v kartě**: dlaždice, souboje a KPI uvnitř
grafu se oddělují rámečkem a mícháním do podkladu, ne druhou vrstvou plochy.

**Ve videu a ve statické grafice plocha nepatří.** Kompozice je celá jedna scéna, rámeček
kolem grafu je tam navíc. Reflex ze seznamu *Takhle to nedělej* míří na tenhle případ,
ne na web.

---

## 2b. Rozvržení hlavičky

Hlavička grafu má dvě podoby a **vybírá se podle obsahu, ne podle vzhledu stránky.**

### Na střed — když graf nemá nic než sebe

Sada barů, jeden koláč, jedna škála. Titulek Display verzálkami na střed, pod ním
podtitulek `--muted` na střed, pod tím data.

```
              HUSTOTA ENERGIE NA KILOGRAM
          Poměr kapacity vůči hmotnosti powerbanky
   ────────────────────────────────────────────────────
   [ bary ]
```

### Vlevo + hlavní údaj vpravo — když se z grafu vytahuje číslo

Peak, průměr, celkem, doba do prahu. Titulek a podtitulek vlevo, vpravo zarovnaný
nahoru **hlavní údaj** (Display, `clamp(26px, 3.4vw, 34px)`) a pod ním popisek
verzálkami v `--muted`.

```
   NÁBĚH TEPLOTY V ČASE                        86,3 °C
   Zátěžový test 35 W · hot spot · 22 °C   MAXIMUM PO 60 MIN
   ────────────────────────────────────────────────────
   [ křivka ]
```

Jakmile má graf „to jedno číslo, kvůli kterému tam je", patří do hlavičky vpravo —
divák ho přečte, aniž by musel luštit křivku. **Míchat obě rozvržení v jednom výstupu
je v pořádku**; řídí se to obsahem grafu, ne konzistencí layoutu.

---

## 3. Barvy

### Kdy stavové a kdy neutrální

Řídí se to pravidlem z `design.md` kapitoly 6: **existuje práh nebo referenční hodnota?**

**Stavové barvy** — zelená, oranžová, červená — použij, když se hodnota čte **proti něčemu**:
proti prahu (86 °C vs. 85 °C), proti deklaraci výrobce (+23 % nad udávaným limitem),
proti minulé generaci nebo minulé ceně. Tam barva nese informaci.

**Modrou nebo neutrální škálu** použij, když jde jen o velikost na škále. Delší sloupec
sám o sobě není „success" — je jen delší.

Prakticky: **sloupce nechávej v modré a šedé, ale hodnotu vedle nich obarvi**, když ji
porovnáváš s prahem. Bar kóduje velikost, číslo vedle něj kóduje stav — dvě různé věci
a je v pořádku, aby měly různou barvu.

### Barevné řady

Při více řadách v jednom grafu:

1. **Hlavní řada** — brand modrá `#1148E6`, nebo Blue 40 `#3873FF` na tmavém pozadí.
2. **Porovnávaná řada** — neutrální šedá, **v dark Gray 70 `#3B3B3B`, v light Gray 30
   `#989898`**.
3. **Třetí a další** — světlejší kroky modré (Blue 30, Blue 20), ne nové odstíny.

⚠️ **Šedá pro konkurenci je tmavá, ne střední.** Gray 40 až 60 v dark režimu působí jako
druhá plnohodnotná řada a bere pozornost testovanému kusu. Šedý bar má být **zapuštěný
do plochy grafu** — čitelný, ale zjevně druhořadý. V light režimu to platí obráceně:
Gray 30 je tam ta tmavší strana.

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
  Konkrétně 1 px v ~12 % barvy textu. **Nulová čára je silnější než zbytek mřížky**
  (~22 %) — je to základna, od které se délka čte, ne další dílek.
- **Jednotky patří k hodnotám**, ne jen do titulku. Divák často vidí jen výřez.
- U měření uveď **podmínky** — teplota prostředí, verze firmwaru, doba zátěže.

---

## 5. Popisky a čísla

- **Přímý popisek místo legendy**, kdykoli to jde. Legenda nutí oči skákat sem a tam.
- **Nechej popiskům místo.** Žádná křivka, čára ani anotace nesmí procházet přes text.
- **Tabulková čísla** (`tnum`) všude, kde se hodnoty porovnávají nebo animují —
  jinak čísla poskakují.
- **Stejná přesnost u rovnocenných hodnot.** Nepiš 3,5 a vedle 3,47.
- Hodnota u sloupce je čitelnější než osa. Když se vejde, dej ji tam a osu zjednoduš.

### Legenda

Přímý popisek je výchozí volba, ale **legenda není chyba** — je správná tam, kde se řada
popsat na místě nedá:

- **referenční čára přes celou šířku** (udávaný limit, práh, průměr třídy) — nemá „místo",
  kam popisek pověsit
- **tři a víc řad**, kde by se přímé popisky trefovaly do sebe
- **řada, která se dotýká jiné** a popisek by musel přeskakovat přes data

Když se legenda použije, má být **tichá** — je to klíč, ne obsah. Nejčastější chyba je,
že klíč přebije data, která popisuje.

| Vrstva | Hodnota |
|---|---|
| text | **11,5 px**, řez Bold 700, barva `--text-2` |
| mezera klíč ↔ text | 6 px |
| mezera mezi položkami | 14 px |
| umístění | pod grafem, zarovnaná k datové ploše |

**Klíč napodobuje tvar toho, co zastupuje.** To je celé pravidlo:

| Typ řady | Klíč |
|---|---|
| **spojnicová (křivka)** | úsečka **14 × 3 px**, rádius 2 px, v barvě řady |
| **spojnicová přerušovaná** | tatáž úsečka, ale **přerušovaná stejným rytmem jako data** — `repeating-linear-gradient(90deg, barva 0 4px, transparent 4px 7px)` |
| **plošná — bar, plocha, buňka, silueta** | zaoblený čtvereček **12–14 px**, rádius ~28 % strany (squircle) |
| **jednotlivý datový bod** | squircle v barvě řady, ve velikosti markeru v grafu |

> **Čtvereček nedávej ke křivce.** Plný 13px čtverec vedle tenké přerušované čáry váží
> opticky víc než samotná data — klíč pak působí jako hlavní prvek legendy. U křivky patří
> úsečka; zaoblený čtvereček zůstává značkovým tvarem na **koncovém bodu křivky**
> a u plošných řad.

### Titulek je jméno testu, ne závěr

**Titulek pojmenovává, co se měří, a napříč recenzemi zůstává stejný.** „Účinnost podle
scénáře", „Náběh teploty v čase", „Hustota energie na kilogram". Čtenář podle něj graf
pozná i v jiné recenzi a o rok později.

**Závěr do titulku nepatří.** „Nad 82 % ve všech scénářích" je zjištění a má vlastní místa:

| Kam se závěr dá | Jak |
|---|---|
| **podtitulek** | jedna věta pod nadpisem, `--muted` |
| **hlavní údaj vpravo** | číslo v hlavičce, viz kapitola 2b |
| **text kolem grafu** | odstavec, který graf uvozuje nebo shrnuje |

Kdyby závěr nesl titulek, měla by každá recenze stejný graf pojmenovaný jinak a nešly by
porovnat — a titulek by se navíc měnil pokaždé, když se přeměří data.

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

- **Zaoblení konce baru — spor s referenční paletou.** Tenhle soubor říká, že bary jsou
  rovné (kapitola 2). Jirkova ukázka `Barevná paleta · Akcenty` má u vodorovných barů
  `border-radius: 0 4px 4px 0`, tedy jemně zaoblený pravý konec. Na 22px baru je to
  drobnost, ale je to rozpor a chce potvrdit u autora identity, která varianta platí.
- **Typy grafů**, které oficiálně používáme — zatím vznikají ad hoc podle potřeby.
- **Heatmapy a rozptylové grafy** — pravidla pro ně nemáme.
- **Patterny v plochách** — čeká na značkovou sadu textur.
- **Srovnávací tabulky** — vztah mezi tabulkou a grafem u stejných dat.
- Chování grafů **na výšku** pro sociální sítě.
