---
name: geekboy-design
description: >
  Použij při tvorbě jakéhokoli vizuálního výstupu GeekBoy — Remotion kompozice, web,
  aplikace, grafy, miniatury, statická grafika, merch. Kompletní systém — identita,
  loga, barvy, typografie, tvarosloví, pohyb i pravidla rozhodování.
version: 2.1
updated: 2026-07-27
font: GeekBoy VF 1.003 · GeekBoy Display ExtraBold
satelity: [motion.md, icons.md, charts.md]
---

# GeekBoy — designový systém

---

## 0. Jak tohle číst

Kompletní designový systém GeekBoy. Vychází z brandového manuálu od **Jirky Chlébuse**
(identita, loga, barvy, písma, idea stylu) a doplňuje ho o pravidla pro tvorbu — poměry,
hierarchii, pohyb a implementaci. **Všechny hodnoty jsou tady, nikam jinam chodit nemusíš.**

Co tu nenajdeš: výpisy jednotlivých souborů, tiskové varianty a kompletní sadu ikon.
Ty jsou v `assets/`, cesty najdeš vždy u příslušné sekce.

**Neměnné konstanty** — písmo GeekBoy, GeekBoy Blue `#1148E6`, tmavé pozadí jako výchozí
a zaoblený čtverec jako signaturní tvar. Bez nich to přestane být GeekBoy. Všechno ostatní
jsou výchozí poměry a směr — přizpůsob je médiu, jen drž celkový charakter.

> **Výjimka — záměrná nápodoba cizího stylu.** Když zadání říká „udělej to jako v Obsidianu
> / ve stylu X", konstanty nevnucuj a řiď se předlohou. Tahle pravidla jsou pro *vlastní*
> výstupy GeekBoy, ne pro imitace. Podrobněji v kapitole *Kdy je v pořádku pravidla porušit*.

Kdyby se dokument někde rozcházel s tím, co reálný font nebo SVG umí, **platí soubor** —
u variabilního písma a ikon jsme na pár takových míst narazili a jsou popsaná u sekcí.

### Pořadí priorit

Když si požadavky odporují, chraň je v tomhle pořadí:

1. **Poctivost dat.** Čísla, jednotky, podmínky testu a výhrady.
2. **Značkové konstanty.** Písmo, GeekBoy Blue, tmavé pozadí, zaoblený čtverec.
3. **Divák pochopí hlavní sdělení do tří vteřin.**
4. **Pozná se, že je to GeekBoy** — i bez loga v rohu.
5. **Kompozice sedne na tenhle materiál**, ne na šablonu z minula.
6. **Detaily** — mezery, pohyb, mikrotypografie.

### Zjednodušit ano, zkreslit ne

Bod 1 neznamená, že do grafu musí jít všechno, co jsi naměřil. Zjednodušení je legitimní
nástroj a často je to ta lepší volba — divák nepotřebuje dvanáct řad, potřebuje pochopit
rozdíl.

**Zjednodušit smíš:** ubrat řady a nechat jen ty, které nesou sdělení · zaokrouhlit ·
sloučit kategorie · zúžit časový rozsah · ukázat jen zajímavou část měření ·
místo grafu použít jednu větu.

**Zkreslit ne:** dělat rozdíl větší nebo menší, než jaký je · useknout osu tak, aby drobný
rozdíl vypadal dramaticky · mlčky vypustit měření, které závěru odporuje ·
doplnit hodnotu, kterou jsi nezměřil.

Test: **kdyby divák viděl kompletní data, změnil by závěr?** Když ne, zjednodušuj klidně.
Když ano, zjednodušení je zkreslení. A když si zjednodušení žádá kontext — jiná osa,
vybraný úsek, chybějící konkurent — napiš to k tomu jednou větou; stačí popisek.

Ptej se, jen když by odpověď změnila význam dat, verdikt, cenu nebo doporučení.
Jinak vynech, poctivě označ a pokračuj.

### Principy

Když si nevíš rady a pořadí priorit na to nestačí, rozhodni podle tohohle:

1. **Krása i srozumitelnost jdou spolu.** Ani jedno zbytečně neobětuj. Když to
   v konkrétním výstupu nejde dohromady, rozhodni podle toho, co divák v ten moment
   potřebuje — rychle pochopit, nebo zaujmout.
2. **Konzistence drží značku.** Nový výstup má jít do pár vteřin poznat jako náš.
3. **Každý prvek má důvod.** Co nic nesděluje, pryč. Prázdné místo je nástroj, ne chyba.
4. **Význam před dekorací.** Barva, akcent i pohyb něco znamenají.
5. **Jedno písmo, jedna brand barva.** GeekBoy a `#1148E6` musí být poznat vždy.

---

# Část I — Kdo jsme

## 1. Ekosystém

GeekBoy není jeden produkt ani jeden YouTube kanál. Je to ekosystém několika projektů,
které mají odlišný účel, ale sdílí stejné hodnoty, vizuální jazyk a způsob komunikace.
**Každý nový výstup musí být jasně zařaditelný do některé z těchto vrstev.**

### Sdílené principy

Všechny projekty stojí na tomtéž:

- objektivita před dojmy
- měření před marketingem
- důvěryhodnost před senzací
- jednoduchost před složitostí
- moderní a čistý vizuální jazyk
- konzistentní typografie, barvy a designový systém
- stejný způsob hodnocení a doporučování produktů

**Změna platformy nebo formátu nikdy neznamená změnu značky.**

### Projekty

| Projekt           | Role                         | Co v něm vzniká                                                                                                          |
| ----------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **GeekBoy**       | hlavní značka a autorita     | recenze, testy, srovnání, nákupní doporučení — nastavuje standard kvality pro celý ekosystém                             |
| **GeekBoy Lab**   | laboratoř a technické zázemí | metodiky testování, benchmarky, experimenty, automatizace, AI nástroje, hlubší analýzy — data, přesnost, transparentnost |
| **GeekBoy Extra** | rozšíření hlavního obsahu    | bonusový obsah, experimentální videa                                                                                     |
| **Web**           | referenční databáze          | domov dlouhodobého obsahu — recenze, výsledky měření, databáze produktů, srovnání                                        |
| **Discord**       | komunitní vrstva             | sdílení zkušeností, diskuze, zpětná vazba — aktivní součást GeekBoy, ne jen komunikační kanál                            |
| **Social media**  | distribuce a objevování      | překlad GeekBoy do jiného formátu, nikdy ne do jiného charakteru                                                         |

### Co se nikdy nemění

Bez ohledu na projekt: logo a identita, typografie, barevný systém, tón komunikace,
objektivní hodnocení, důvěryhodnost, práce s daty, vizuální konzistence.

---

## 2. Charakter a tón

**Co děláme:** testujeme a recenzujeme herní a tech hardware. Smysl každého výstupu je dát člověku **rychlý, důvěryhodný verdikt** a oporu pro rozhodnutí o koupi.

**Pro koho:** lidé zvažující nákup herního nebo tech vybavení — od nadšenců po běžné
kupující. Chtějí rychle vědět „stojí to za to?" bez balastu, ale s pocitem, že za tím stojí
někdo, kdo tomu rozumí.

**Co si má člověk odnést:** *„tihle tomu rozumí a dá se jim věřit."* Hlavní emoce je důvěra
a kompetence, ne hype.

### Kdyby byl GeekBoy člověk

| Jsme | Nejsme |
|---|---|
| odborní | křiklaví |
| moderní | agresivní |
| sebevědomí | chaotičtí |
| věcní | odtažití / přehnaně formální |
| čistí | laciní |

**Tón:** odborný a moderní, ale přístupný — mluvíme jako někdo, kdo tomu fakt rozumí a umí
to vysvětlit. Ne jako manuál, ne jako křečovitý influencer.

**Vizuální styl:** minimalistický a vzdušný. Radši méně prvků a víc prostoru
než přeplněná plocha.

---

## 3. Idea vizuálního stylu — zaoblený čtverec

Vizuální styl GeekBoy vychází z jednoduchého zaobleného čtverce, který propojuje svět
hardwaru a softwaru. Připomíná zároveň **klávesu**, **ikonu aplikace** i **rámeček** zaměřující pozornost na to podstatné. Tento signaturní tvar je začleněný do loga, typografie i dalších prvků identity a vytváří jednotný a snadno rozpoznatelný vizuální jazyk.

Není to jen součást loga. Je to stavební prvek celého designového systému — a je to důvod,
proč mají všechna zaoblení, odrážky a markery v tomhle dokumentu tvar, jaký mají.

### Jak s ním pracovat

Používáme ho jako **jemný podpis značky**. Nemá být dominantním motivem každé obrazovky
ani dekorací bez účelu. Objevuje se tam, kde přirozeně nahrazuje běžné geometrické tvary
a současně pomáhá sjednotit vizuální jazyk.

Typické použití: odrážky a seznamy · legendy grafů · markery datových bodů · callouty
a zvýraznění · pozadí ikon · masky obrázků · halftone vzory · drobné animační prvky.

> **Pravidlo:** kdyby na daném místě běžně vznikl kruh, tečka nebo obyčejný čtverec,
> zvaž náš zaoblený motiv.

### Méně je více

Síla motivu je v opakování, ne v množství. V jedné kompozici zpravidla stačí několik dobře
umístěných prvků, které značku připomenou. Jakmile začne být dominantním motivem celé
obrazovky, ztrácí účinek a působí dekorativně.

Zaoblený čtverec má být detail, kterého si divák často ani vědomě nevšimne, ale který
podvědomě vytváří konzistentní rukopis GeekBoy.

### Geometrie podle velikosti

Zaoblení se přizpůsobuje velikosti prvku:

- **Malé prvky** (odrážky, legendy, markery) → výraznější zaoblení typu **squircle**.
  V malém měřítku působí opticky vyváženěji než klasický rádius.
- **Větší plochy** (segmenty grafů, datové buňky, masky) → jemnější zaoblení
  přibližně **11 % velikosti strany**, takže si zachovají charakter čtverce.

Nejde o přesná čísla, ale o optický princip: **čím menší prvek, tím měkčí zaoblení;
čím větší prvek, tím víc má připomínat čtverec.**

### Charakter rohů

Rohy jsou u nás **jemně zaoblené** — ani ostré hrany, ani výrazné bubliny. To je výchozí
stav a platí, dokud není důvod pro jedno z dvou vědomých vybočení:

- **pilulkové štítky** — plně kulaté konce, protože se čtou jako popisek, ne jako plocha
- **hranaté spec karty** — ostré rohy, protože se čtou jako záznam v protokolu
  (viz kapitola 9)

Obě výjimky mají důvod ve funkci prvku, ne v estetice. Když se přistihneš, že měníš
zaoblení kvůli vzhledu, vrať se k jemnému.

---

# Část II — Konstanty

## 4. Logo

### Která varianta kdy

| Varianta | Kdy ji použít |
|---|---|
| **GeekBoy Logo** | výchozí varianta — web, video, aplikace, sociální sítě |
| **GeekBoy Logo™** | jen tam, kde je potřeba uvádět ochrannou známku |
| **Vertical** | když není dost horizontálního prostoru |
| **Lab** | experimentální projekty, interní nástroje, GeekBoy Lab videa |
| **Extra** | sekundární YouTube kanál |

Ve většině případů sáhni po hlavním logu. Lab a Extra patří jen ke svým projektům — nejsou
to dekorativní varianty. Od Lab i Extra existují také vertikální verze.

### Světlá a tmavá verze

Logo existuje ve dvou barevných verzích a pozná se podle názvu souboru: `logo-light-*` je
černé pro světlá pozadí, `logo-dark-*` je bílé pro tmavá. Jinou barevnou verzi nemáme
a přebarvovat se nesmí — **na modrém pozadí `#1148E6` se proto používá bílá verze.**

### Minimální velikost a ochranná zóna

| | Minimální výška na obrazovce |
|---|---|
| Logo | 20 px |
| Lab | 24 px |
| Extra | 24 px |

**Ochranná zóna: 50 % výšky loga** ze všech stran. V té ploše nesmí být žádný text,
grafika ani okraj.

### Čemu se vyhnout

- neměnit proporce
- nepřekreslovat logo
- nepoužívat jiné barvy
- nepřidávat stíny
- neotáčet
- nepoužívat efekty
- neumisťovat na nečitelné pozadí

### Kde jsou soubory

```
assets/logos/
  logo-light-logo.svg              logo-dark-logo.svg
  logo-light-logo-tm.svg           logo-dark-logo-tm.svg
  logo-light-logo-na-vysku.svg     logo-dark-logo-na-vysku.svg
  logo-light-lab-logo.svg          logo-dark-lab-logo.svg
  logo-light-lab-logo-na-vysku.svg logo-dark-lab-logo-na-vysku.svg
  logo-light-extra-logo.svg        logo-dark-extra-logo.svg
  logo-light-extra-logo-na-vysku.svg  logo-dark-extra-logo-na-vysku.svg
  geekboy-*-cmyk.pdf               ← tiskové CMYK verze
```

---

## 5. Písmo

**GeekBoy** je značkové písmo na všechno — text i nadpisy. I „kód" sázíme GeekBoyem,
ne monospace; drží to jednotu.

**GeekBoy Display** je speciálně upravený ExtraBold řez, kde je v písmenech „O" a „o"
použitý zaoblený čtverec z loga. Používá se **pouze na hlavní nadpis stránky nebo na hlavní
nadpis grafu či statistiky** — a vždy **verzálkami**.

### Kombinace písem a řezů

| Aplikace | Písmo | Nastavení |
|---|---|---|
| Hlavní H1 nadpis | GeekBoy Display | ALL CAPS |
| Ostatní nadpisy | GeekBoy Bold (700) | case sensitive |
| Texty | GeekBoy Regular (400) | case sensitive |

### Používané řezy

**Regular (400) · Regular Italic (400) · Bold (700) · Bold Italic (700)**, plus
**GeekBoy Display ExtraBold (800)** na H1.

Variabilní soubor umí celý rozsah 200–900, ale my používáme jen tyhle. Důsledek, se kterým
je potřeba počítat: **hierarchii pod úrovní H2 nedělej vahou, ale velikostí a barvou** —
mezistupně jako Medium nebo SemiBold k dispozici nemáme.

**Náhradní písmo**, když GeekBoy není k dispozici: Arial (Windows), Helvetica nebo
San Francisco (Mac). Ve sdílených online dokumentech (Google Docs a podobně) používáme
**Hubot Sans**.

### Hierarchie velikostí

Základ je běžný text = **1×**. Všechno ostatní je jeho násobek, takže systém sedí na
jakékoli plátno — pro web je `1× ≈ 17 px`, pro video si zvol základ podle plátna
a vynásob.

```
velký nadpis (H1)   ~2,2× – 3,4×   GeekBoy Display 800, VERZÁLKY
nadpis (H2)         ~1,3× – 1,5×   Bold 700
podnadpisy (H3–H6)  ~1,1× → 0,9×   Bold 700, postupně menší a tlumenější
ZÁKLAD — text       1×             Regular 400, řádkování ~1,6
podtitul / lead     ~1,05× – 1,4×  Regular 400, tlumená barva
malé / popisky      ~0,7× – 0,9×   meta, štítky, poznámky
```

- **Řádkování** je poměr k velikosti: text vzdušný (~1,6), nadpisy sevřené (~1,1–1,25).
  Čím větší písmo, tím menší řádkování.
- **Tracking** v `em`: velké nadpisy lehce do minusu, verzálkové popisky rozprostři
  (+0,04 až +0,06 em).
- **Verzálky** jen na H1 a na drobné značkové popisky — štítky, záhlaví tabulek,
  zdroj citace.
- **Délka řádku** ≈ 40× velikost základního písma.

### OpenType featury

Značkové detaily jsou přímo v písmu. Většinu z nich dostaneš tím, že je **nevypneš**.

| Feature | Co dělá | Jak s ní |
|---|---|---|
| *výchozí stav* | tečkovaná nula, čtvercová odrážka | **nevypínat** — je to signaturní detail z loga |
| `tnum` | tabulková čísla | **zapínat** v tabulkách, grafech a všude, kde se čísla porovnávají nebo animují |
| `ss02` | alternativní malé `l` | zapínat na H1 |
| `ss03` | alternativní `r` | zapínat na H1 |
| `ss04` | bezpatkové velké `I` | zapínat na H1 a H2 |
| `ss05` | prázdná nula | **nepoužívat** — ruší značkovou tečkovanou nulu |
| `ss06` | kulaté odrážky | **nepoužívat** — výchozí odrážka je zaoblený čtvereček, tedy náš mikro-motiv; `ss06` ho zahodí |
| `ss01` | hranaté tečky, alternativní `a`, `y`, `Q` | volitelné |
| `frac`, `numr`, `dnom`, `sups`, `subs`, `case` | zlomky, indexy, verzálková interpunkce | podle potřeby |

**Tečkovaná nula** odlišuje číslici `0` od velkého `O` — u názvů produktů, kódů
a technických parametrů je to zásadní. Nechávej ji zapnutou.

### Technikálie variabilního fontu

| Osa | Rozsah | Pozn. |
|---|---|---|
| `wght` | 200 → 900 | používáme 400 a 700 |
| `wdth` | 80 → 120 | drž 100; 80 (Condensed) jen jako záměrný akcent |
| `ital` | 0 → 1 | kurzíva je osa, ne zvláštní soubor |

- **Výchozí instance souboru je Condensed ExtraLight** a font se tak i jmenuje. V CSS to
  nevadí, ale ve Figmě a Illustratoru je nutné vybrat instanci ručně.
- V `@font-face` vždy deklaruj `font-weight: 200 900` a `font-stretch: 80% 120%` —
  bez toho `font-stretch` vůbec nefunguje.
- Kurzívu zapínej přes `font-variation-settings: "ital" 1`, ne přes `font-style: italic`.

### Kde jsou soubory

```
assets/fonts/
  geekboy-vf.woff2 · geekboy-vf.ttf · geekboy-vf.woff      ← variabilní, výchozí volba
  geekboydisplay-extrabold.woff2 · .otf                     ← Display na H1
  geekboy-regular.* · geekboy-bold.* · geekboy-italic.* …   ← statické řezy, když VF nejde
```

---

## 6. Barvy

### Barva není dekorace

Používáme ji jen tehdy, když pomáhá lépe pochopit informaci, zvýraznit akci nebo vytvořit
jasnou vizuální hierarchii. **Pokud stejného výsledku dosáhneš typografií nebo prostorem,
další barvu nepřidávej.** Hierarchii stavěj nejdřív typografií, teprve potom plochou a barvou.

### Kdy smí číslo dostat stavovou barvu

Rozhoduje jediná otázka: **existuje práh nebo referenční hodnota, vůči které to čteme?**
Když ano, barva nese informaci a patří tam. Když ne, je to dekorace.

**Obarvit smíš:**

| Případ | Příklad |
|---|---|
| **hodnota vůči prahu nebo limitu** | 86 °C proti prahu 85 °C → červená · 74 °C v pásmu 70–85 °C → oranžová |
| **měření vůči deklaraci výrobce** | vypne až 23 % nad udávaným limitem → zelená · rozměry mimo toleranci → červená |
| **směr změny** | zlevnění → zelená · zdražení → červená · vyšší výkon proti minulé generaci → zelená |
| **ověřeno / neověřeno / chybí** | podporované protokoly |

**Neobarvuj:**

- **prostou velikost na škále.** Delší sloupec není „success", je jen delší. Vyšší hustota
  výkonu bez srovnání s třídou je číslo, ne stav.
- **náš verdikt.** *Doporučený produkt* nebo *skóre 9,0* je názor. Ten patří brand akcentu
  nebo neutrálu, ne zelené — zelená by z hodnocení dělala měření.
- **rozdíl bez referenčního bodu.** „O 17 % větší než Anker" je fakt, ne stav; menší ani
  větší tady není lepší.

Test: **kdyby barva zmizela, přišel bys o informaci, nebo jen o důraz?** Když o důraz,
patří tam typografie, ne barva.

**GeekBoy Blue je jediná identifikační barva značky. Nikdy nezaváděj druhou podobnou modrou.**

### Hlavní barvy

| Název | HEX | RGB |
|---|---|---|
| **GeekBoy Blue 50** | `#1148E6` | 17, 72, 230 |
| **GeekBoy Black** | `#0B0B0B` | 11, 11, 11 |

### Královská modrá

| Krok | HEX | | Krok | HEX |
|---|---|---|---|---|
| Blue 100 | `#000330` | | Blue 40 | `#3873FF` |
| Blue 90 | `#000B54` | | Blue 30 | `#5995FF` |
| Blue 80 | `#031D70` | | Blue 20 | `#86B6FF` |
| Blue 70 | `#062B95` | | Blue 10 | `#BAD6FF` |
| Blue 60 | `#0B3ABD` | | Blue 0 | `#EEF4FF` |
| **Blue 50** | **`#1148E6`** | | | |

### Antracit

Pozadí, text, plochy, linky. Nemusíš použít všech 11 kroků — vyber tmavou, světlou
a jednu až dvě mezilehlé.

| Krok | HEX | | Krok | HEX |
|---|---|---|---|---|
| Gray 100 | `#0B0B0B` | | Gray 40 | `#7C7C7C` |
| Gray 90 | `#1A1A1A` | | Gray 30 | `#989898` |
| Gray 80 | `#2A2A2A` | | Gray 20 | `#B6B6B6` |
| Gray 70 | `#3B3B3B` | | Gray 10 | `#D4D4D4` |
| Gray 60 | `#4D4D4D` | | Gray 0 | `#F3F3F3` |
| Gray 50 | `#606060` | | | |

### Stavové barvy

Sémantické barvy pro stavy a zpětnou vazbu u testovaných produktů. Každá má sytou
`primary` na výplně a dvě tlumené plochy.

| Význam | primary | plocha · dark | plocha · light |
|---|---|---|---|
| **Ověřeno / dobře** | `#31C96E` | `#061912` | `#E7F7EC` |
| **Výstraha** | `#FF792E` | `#251200` | `#FFF1E9` |
| **Nejhorší / špatně** | `#FF404A` | `#2B0B0B` | `#FFF1F2` |

`primary` je stejná v tmavém i světlém režimu. Na světlém pozadí používej jako **text**
spíš tmavou variantu, sytou nech na výplně a bary.

**Význam nikdy nenes jen barvou.** Doplň ho tvarem, ikonou nebo popiskem, ať to funguje
i černobíle a pro barvoslepé.

### Jak stavovou barvu složit

Tohle je nejčastější místo, kde stavová barva zaskřípe: sytá `primary` se použije jako
velká plocha a výsledek křičí. **Sytá barva patří na malé plochy a na text, ne pod odstavec.**

Recept — v dark režimu, v light se prohodí `plocha · dark` za `plocha · light`:

| Vrstva | Čím |
|---|---|
| **plocha** | `plocha · dark` (např. `#061912` u zelené) — tmavá varianta téhož odstínu |
| **text a číslo** | `primary` |
| **tečka, lišta, ikona** | `primary` |
| **rámeček** | 40–50 % `primary` smíchaných s běžným `--border` |
| **plný odznak** | `primary` jako výplň, text v `plocha · dark` — jen na malý štítek |

Klíč je, že **plocha je tmavá varianta stejného odstínu**, ne neutrální `--surface`
s barevným rámečkem. Zelený stav na tmavě zeleném podkladu se čte jako celek; zelený
rámeček kolem šedé plochy se rozpadá na dva prvky.

### Dva tvary stavu — s plochou a bez ní

| Tvar | Kdy | Provedení |
|---|---|---|
| **Stavová plocha** | samostatný prvek, který má být vidět zvlášť — spec karta, chip v souhrnu, callout | plocha · dark + `primary` text + lišta nebo tečka |
| **Inline stav** | hustý kontext, kde by plochy vytvořily šachovnici — řádky tabulky, seznamy, legendy | **žádná plocha**: text v `primary` řezem Bold + tečka v `primary` s jemným prstencem v `plocha · dark` |

Inline tvar drží, protože barvu nese **tučný text**, ne plocha — v tenkém řezu by to
nefungovalo. A neutrální stav (*offline*, *neměřeno*, *nemáme data*) se v obou tvarech
kreslí `--muted`, ne červeně. **Chybějící údaj není chyba produktu.**

### Světlý a tmavý režim

**Dark je výchozí varianta.** Light používáme omezeně — na velmi světlé scény, do tiskovin
a tam, kde to vyžaduje kontext. Brand i stavové barvy drží v obou režimech, mění se jen
neutrály: v dark tmavé pozadí a světlý text, v light obráceně.

### Sémantické tokeny

Komponenty nesahají přímo na `blue-*` a `gray-*`, ale na tyhle role. Režim se přepíná
atributem `data-theme="dark|light"`.

| Token | Dark | Light | Význam |
|---|---|---|---|
| `--bg` | Gray 100 | Gray 0 | pozadí stránky |
| `--surface` | Gray 90 | `#FFFFFF` | karty, panely |
| `--border` | Gray 80 | Gray 20 | linky, rámečky |
| `--text` | Gray 10 | Gray 100 | hlavní text |
| `--muted` | Gray 40 | Gray 50 | tlumený text |
| `--accent` | Blue 50 | Blue 50 | CTA, odkazy, akcent |
| `--accent-text` | Blue 40 | Blue 50 | akcentní popisky a odkazy v textu |
| `--accent-dim` | Blue 90 | Blue 0 | tlumená plocha z akcentu — štítky, callouty |
| `--link-hover` | Blue 40 | Blue 70 | odkaz při najetí |
| `--good` / `--warn` / `--bad` | primary | primary | stavy |

**Nevymýšlej nová jména tokenů.** Když žádný nesedí, použij vlastní předponu
(`--rev-*`, `--yt-*`) a napiš proč — ať je vidět, že jde o výjimku, ne o nový standard.

---

# Část III — Jak rozhodovat

## 7. Co má výstup odpovědět

Než sáhneš po layoutu, rozhodni, **jaký problém řeší člověk na druhé straně.**
Univerzální šablona neexistuje — a šablona z minulého videa je jen setrvačnost, ne řešení.

### Jedna hlavní otázka

Každý výstup odpovídá na **jednu** hlavní otázku. Pojmenuj si ji dřív, než začneš skládat
obrazovku:

- *Vyplatí se to?*
- *Je to lepší než konkurence?*
- *Komu to doporučit?*
- *Co je největší kompromis?*

Když výstup odpovídá na tři otázky najednou, neodpovídá pořádně na žádnou. Rozděl ho,
nebo vyber tu, která je pro diváka nejcennější.

### Otázka určuje kompozici

Teprve z otázky plyne, co má na ploše dominovat:

| Co člověk řeší | Co dominuje |
|---|---|
| **Porovnání produktů** | oba produkty vedle sebe na stejné vizuální bázi — rozdíl má být vidět, ne dopočítaný z textu |
| **Benchmark nebo měření** | graf; čísla kolem něj jen podpírají |
| **Recenze** | produkt; data podporují, ale nevedou |
| **Výběr nejlepšího** | verdikt nahoře, zdůvodnění pod ním |
| **Jedno silné zjištění** | to zjištění samo — velké, bez okolí, které by s ním soupeřilo |

Pomůcka: pojmenuj si nejobvyklejší řešení pro tenhle typ výstupu a **odmítni ho, pokud si
ho materiál nezaslouží.** Ne každá recenze musí vypadat jako každá recenze.

---

## 8. Hierarchie sdělení

Každý výstup má mít jasné úrovně:

- **Level 1 — toho si musí všimnout každý.** Hlavní sdělení, verdikt, titulek. Největší,
  nejvýraznější, klidně brand akcent. Ideálně *jedna* věc.
- **Level 2 — to pochopí většina.** Podpůrný kontext, klíčové parametry.
- **Level 3 — detail pro zájemce.** Specifikace, poznámky — tlumeně, menší.

Test: *„Co může zmizet bez ztráty hlavního významu?"* → to je Level 3.

### Dvě rychlosti čtení

Tentýž obsah vydáváme ve dvou médiích a každé má jiného čtenáře:

- **Cesta diváka** — video, miniatura, story. Verdikt musí projít **bez pauzy, do tří
  vteřin**: titulek, číslo, barva stavu.
- **Cesta čtenáře** — recenze, tabulka, metodika. Přesná čísla, podmínky měření, zdroje.

**Každé tvrzení má jeden domov.** Tabulka smí nést přesnost, ale druhý souhrn stejné váhy,
který říká totéž, je chyba — ne důkladnost.

---

## 9. Plochy, karty a prostor

### Surface musí mít důvod

Pozadí, rámeček, panel a karta existují jen tehdy, když něco skutečně komunikují —
výběr, interakci, varování, kontrast nebo skutečné seskupení. **Ne proto, že „se to musí
nějak oddělit".**

### Nepoužívej karty jen kvůli oddělení

Než sáhneš po rámečku nebo boxu, zkus prostor, zarovnání, typografii a změnu hustoty.
Místo

> šedá karta / šedá karta / šedá karta

radši

> nadpis · prostor · obsah · prostor · nadpis

Stránka je normálně jedna souvislá plocha. Karty v kartách nedělej.

### Barevná plocha se míchá do podkladu

Platí pro brand modrou stejně jako pro stavové barvy: **`primary` není podklad.**
Když má plocha nést barvu — vítěz v souboji, vybraná varianta, zvýrazněný řádek —
nesahej po syté barvě, ale po jedné z těchto dvou možností:

- **8–18 % barvy smíchaných do podkladu**, na kterém plocha leží
- **tmavá varianta odstínu** (`plocha · dark`, u modré Blue 90 `#000B54`)

Identitu plochy pak dotáhne **rámeček** (40–50 % barvy smíchaných s `--border`),
**barevný nadpis nebo číslo** (`--accent-text`, resp. `primary`) a případně **malý plný
odznak**. Odznak je jediné místo, kde smí být sytá barva jako výplň — je malý a nese text.

> Pravidlo: čím větší plocha, tím míň barvy. Sytá `#1148E6` pod celou kartou přebije
> všechno okolo a zbytek kompozice ztratí hierarchii.

### Zaoblení

Vychází ze zaobleného čtverce (kapitola 3), konkrétní hodnoty pro web:

| Prvek | Rádius |
|---|---|
| karty, hero, callouty | 12 px |
| tlačítka | 10 px |
| štítky, přepínače | pilulka (999 px) |
| datové čtverečky, buňky | 11 % strany prvku |
| odrážky, legendy, markery | squircle |

Mimo web nejde o pixely, ale o **poměr zaoblení k velikosti prvku**.

### Záznam, nebo měření? — spec karta vs. datová dlaždice

Obojí nese stavovou barvu a obojí vypadá v návrhu podobně, ale jsou to **dvě různé
komponenty a pletou se nejčastěji ze všeho.** Rozhodni jedinou otázkou:

> **Čtou se položky proti sobě, nebo každá zvlášť?**

| | **Spec karta** (hranatá) | **Datová dlaždice** (zaoblená 12 px) |
|---|---|---|
| Položky jsou | různorodé — každá o něčem jiném | **táž veličina** změřená na víc místech |
| Hodnota je | stav nebo text — *ověřeno*, *chybí*, `5/9/12 V` | **číslo na společné škále** — 86,3 °C · 74,0 °C |
| Barva kóduje | diskrétní stav | **pásmo na škále** |
| Čtou se | jedna po druhé, jako položky seznamu | **všechny naráz, jako rozložení** |
| Sousedství | nic neznamená, pořadí je libovolné | **je to informace** — kde je nejtepleji |
| Charakter | záznam v protokolu | mikro-graf |

**Spec karta = záznam.** Podporované protokoly, výsledky dílčích testů, klady a zápory,
poznámka z labu. Provedení:

- **bez zaoblení, ostré rohy**
- **plocha** = tlumená stavová plocha (`plocha · dark`, resp. `plocha · light`)
- **levá lišta 3 px** v syté barvě stavu — ověřeno, výstraha, chybí
- **verzálkový popisek** nahoře vlevo, **štítek** vpravo (ten zaoblený zůstává)
- **hodnota** pod tím, Bold, případně s tabulkovými čísly
- skládají se do mřížky; položka, která je zásadní, může zabrat celou šířku

*Proč hranaté:* čtou se jako **záznam v protokolu**, ne jako plovoucí karta v rozhraní.
Ostré hrany na sebe v mřížce navazují a drží tabulkový dojem — zaoblení by z měření udělalo
UI komponentu. Identifikaci obstará barevná lišta.

**Datová dlaždice = měření na společné škále.** Teploty po zónách, spotřeba v režimech,
hodnoty téhož parametru napříč scénáři. Provedení:

- **zaoblení 12 px** jako běžná karta
- **plocha** = tlumená stavová plocha podle pásma, **rámeček** 40 % barvy stavu
- **číslo velké a na střed** (Display, `tnum`), pod ním popisek verzálkami v `--muted`
- pásma vysvětli jednou větou nad mřížkou — *„zelená do 70 °C, oranžová 70–85, červená nad"*

*Proč zaoblené:* nejsou to záznamy, ale **body jednoho měření**. Zaoblení je od sebe
odděluje jako samostatné hodnoty a mřížka pak čte jako sada výsledků, ne jako protokol.

**Nemíchej oba tvary v jednom výstupu pro tutéž roli.** Když jsou protokoly hranaté
a teplotní zóny zaoblené, je to správně — nesou různé věci. Když je hranaté všechno,
stránka se slije do jednoho protokolu a ztratí se, co je záznam a co měření.

> **A ještě jedna možnost: nemá to být rovnou graf?** Jakmile je položek pět a víc a jsou
> to čísla na společné škále, platí *geometrie před komponentou* (kapitola 15) — délka na
> společné škále ukáže rozložení líp než mřížka dlaždic, ve které musí oko porovnávat
> čísla. Dlaždice zvol, když jsou hodnoty **vázané na místo nebo režim**, který se nedá
> seřadit; graf, když se seřadit dá.

### Prostor

Prázdné místo je nástroj, ne chyba. Má zesilovat hlavní prvek. Velké prázdné obdélníky
vzniklé nedoplněným rozvržením nebo osiřelou třetí položkou jsou chyba layoutu — přeskládej
je. Nepoužívej jednu univerzální mezeru mezi všechno; vzdálenost vyjadřuje vztah:

- nadpis → jeho první odstavec: blízko
- odstavec → odstavec: jeden rytmus textu
- skupina obsahu → nová sekce: výrazně víc
- popisek → to, co popisuje: dost blízko, aby se to četlo dohromady

---

## 10. Takhle to nedělej

### Reflexy generátoru

Tohle vzniká, když se nepřemýšlí. Většinu z toho vyplivne generátor sám od sebe —
a pozná se to na první pohled.

**Kompozice**

- Centrovaný hero s obecným textem a pod ním mřížka stejně velkých karet.
- Karta uvnitř karty. Rámeček jako náhrada za slabou hierarchii.
- Zaoblený obdélník kolem každého bloku bez rozdílu — i tam, kde nic neseskupuje.
  **Pozor, graf je výjimka:** na webu je vymezená plocha grafu správně, viz kapitola 15.
- Stejná silueta všech sekcí — pak žádná nic neznamená.
- Řada stejně velkých metrik, když je ve skutečnosti důležitá jen jedna.
- Sekce, které se jmenují podle žánru („Úvod", „Závěr", „Shrnutí") místo podle toho,
  co se v nich stalo.
- Opakovaný souhrn, který říká totéž co tabulka nad ním.

**Ozdoby**

- Štítek nebo pilulka na běžná metadata — datum, kategorie, autor. Štítek je pro **stav**.
- Ikona v barevné dlaždici bez funkce. Ikony různých stylů vedle sebe. Emoji místo ikony.
- Stock fotky, generované ilustrace, abstraktní tvary, falešné screenshoty.
- Hero obrázek jen proto, že sekce „musí něco mít".
- Dekorativní gradienty a záře.

**Data**

- Graf jako dekorace. Bar použitý jako oddělovač.
- Legenda tam, kde stačí přímý popisek u křivky.
- Sloupce jen proto, že existují čísla — když by stačila věta nebo tabulka.
- Drobný šedý text jen proto, aby se obsah vešel.

### Porušení značky

- Druhá „skoro stejná" modrá vedle `#1148E6`.
- Jiné písmo než GeekBoy. Monospace na kód.
- Display na běžný text, nebo naopak H1 běžným řezem.
- Ruční HEX v komponentě místo tokenu.
- Přebarvené, otočené nebo zdeformované logo.
- Barva použitá jako ozdoba, ne jako význam.

### Amatérský pohyb

- Lineární easing. Všechno najednou a stejně dlouho.
- Bounce a velký overshoot. Prvek, co po příletu dál poskakuje.
- Animace `width` nebo layoutu místo `transform` a `opacity`.
---

## 11. Kdy je v pořádku pravidla porušit

Systém má držet značku, ne svazovat ruce. Jsou situace, kdy je správné se od něj odchýlit —
vědomě a s důvodem:

- **kolaborace** s jiným tvůrcem nebo značkou
- **partner branding** — když je výstup společný
- **imitace cizího UI** — „udělej to jako v Obsidianu / jako web X"
- **retro styl** — když je dobová estetika součástí sdělení
- **meme a vtip** — humor si žádá vlastní jazyk
- **aprílové a jednorázové video**
- **experiment**, u kterého chceš zjistit, jestli něco funguje líp

Co platí i při odchylce: **fakta, důvěryhodnost a čitelnost.** Odchýlit se smíš od formy,
ne od poctivosti. A odchylka je vždy **jednorázová** — nezakládá nový standard, dokud se
tak nerozhodneme a nezapíšeme to sem.

---

## 12. Než to odevzdáš

**Podívej se na výsledek, ne na kód.** Vyrenderuj snímek — `npx remotion still` u kompozice,
screenshot u webu — a projdi ho v tomhle pořadí:

1. **První pohled.** Kdyby divák viděl jen první snímek, zapamatuje si hlavní zjištění
   nebo verdikt — nebo jen titulek a náladu?
2. **Kompozice.** Je tam jeden dominantní prvek? Posouvá každá sekce sdělení dál?
   Není některé prázdné místo náhodné?
3. **Typografie.** Mají rovnocenné prvky stejnou velikost, váhu i řádkování? Zarovnává se
   to na společné linky? Vychází mezery ze vztahů, ne z jedné univerzální hodnoty?
4. **Data.** Dokazuje geometrie to tvrzení? Jsou popisky čitelné a osy poctivé?
   Neopakuje se něco, aniž by to odpovídalo na novou otázku?
5. **Střídmost.** Dá se odebrat plocha, rámeček, štítek, ikona, popisek, barva nebo celý
   odstavec, aniž by se ztratil význam? Když ano, odeber.
6. **Režimy a šířky.** Mají light a dark stejnou hierarchii a kontrast? Přeskládá se to na
   úzké obrazovce bez přetečení a lámání slov?
7. **Důvěra.** Sedí jednotky, podmínky měření, zdroje a výhrady?

Oprav **nejzávažnější systémovou vadu**, vyrenderuj znovu a opakuj, dokud nezbude nic
podstatného.

> **Kontrolu si nech pro sebe.** Odevzdává se hotový výstup — ne hodnoticí tabulka,
> deník práce ani sebekritika. Když je něco vědomě nedodělané, stačí jedna věta.

---

# Část IV — Řemeslo

## 13. Pohyb → `motion.md`

GeekBoy pohyb je **přesný nástroj, který měří realitu** — ne hravá animace. Pohyb vede
pozornost a pak ztichne. Když pro animaci nemáš důvod, vynech ji.

Tři kanonické křivky:

```
uiReveal     [0.16, 1, 0.3, 1]    vstupy: fade/scale, řádky, karty, tooltipy
dataGrowth   [0.22, 1, 0.36, 1]   data: sloupce, hodnoty, kreslení křivky
layoutMove   [0.4, 0, 0.2, 1]     přesuny UI, resize, reorder
```

Nikdy lineární interpolace u viditelného prvku. Rychlý nástup, dlouhý jemný doběh.
Prvek dorazí a **drží klid**.

Na webu a v aplikacích je výchozí stav klid — tam pohyb jen vysvětluje změnu stavu.
Ve videu platí pravidla výš.

**Plný spec** — délky, vzdálenosti, stagger, fps-determinismus, kompletní easing — je
v `motion.md`. U kompozice, kde se cokoli hýbe, si ho přečti.

---

## 14. Ikony a obrazový materiál → `icons.md`

Předvybraná sada 253 statických ikon. Jde o open-source ikony **Lucide** převedené na
plochy, takže se dají přebarvovat. Ikony `research`, `fps` a `dollar` jsou vlastní.

**Barvy:**

| Režim | Ikony | Text u nich |
|---|---|---|
| Dark (výchozí) | Blue 40 `#3873FF` | Gray 10 `#D4D4D4` |
| Light | Blue 50 `#1148E6` | Gray 100 |

**Technická poznámka.** Všechny cesty v SVG mají natvrdo `fill:#000000`, takže
`currentColor` na kořeni nic neudělá. Přebarvuj přes CSS masku nebo fill při buildu
odstraň. Ikony mají `viewBox 24 × 24`.

Soubory: `assets/images/*.svg`, kompletní balíček `assets/others/geekboy-icon-set.zip`.
Rozdělení do skupin a mapování *veličina → ikona* je v `icons.md`.

### Ikona není dekorace

Ikonu použij, když **znatelně zrychlí rozpoznání** — kategorie parametru ve specifikaci,
stav, typ konektoru. Jinak dej přednost textovému popisku; slovo je jednoznačnější
než piktogram.

Zaoblený čtverec jako **podklad pod ikonou** (kapitola 3) je v pořádku tam, kde ikona něco
označuje — třeba marker kategorie v tabulce. Není v pořádku jako barevná dlaždice, která
jen zaplňuje místo. Rozdíl je v tom, jestli po odebrání ikony přijdeš o informaci.

### Obrazový materiál

Fotky produktu, screenshoty, diagramy a výstupy z měření používej tehdy, když jsou
**důkaz** nebo skutečně zlepší pochopení.

**Nikdy:** stock fotky · generované ilustrace · abstraktní tvary · falešné screenshoty
produktu · hero obrázek jen proto, že sekce „musí něco mít".

U fotky, která slouží jako důkaz, uveď podmínky — čím a za jakých okolností vznikla.

---

## 15. Grafy a data → `charts.md`

Pravidla, která platí vždy:

1. **Geometrie před komponentou.** Nejdřív zvol vizuální proměnnou — velikost a pořadí →
   délka na společné škále, vývoj v čase → vodorovné pořadí, podíl → proporce, práh →
   vzdálenost od hranice. Teprve pak vyber typ grafu. Nesahej po sloupcích jen proto,
   že existují čísla.
2. **Tabulková čísla** (`tnum`) všude, kde se hodnoty porovnávají nebo animují.
3. **Přímé popisky místo legendy**, kdykoli to jde.
4. **Bary jsou rovné.** Sloupce a pruhy nezaobluj — ostré hrany působí nadčasově
   a zaoblený konec opticky zkracuje délku, tedy to jediné, co bar kóduje.
5. **Zaoblený čtvereček** je koncový bod datové křivky a klíč v legendě. Výchozí barva
   je brand `#1148E6`; v barevně kódovaném grafu ale nese **barvu své řady**.

### Graf na webu má vlastní plochu

**Na webu a v aplikacích graf stojí na vymezené ploše** — jemně odlišený podklad, 1px
rámeček, zaoblení kolem 16 px. Není to karta pro parádu: stránka recenze střídá odstavce,
tabulky a grafy, a bez vymezení splyne graf s textem. Plocha říká „tady se čtou data".

**Ve videu a ve statické grafice plocha nepatří** — kompozice je celá jedna scéna a rámeček
kolem grafu je tam navíc. To je ten reflex ze seznamu *Takhle to nedělej* (kapitola 10);
platí pro kompozice, ne pro web.

### Titulek grafu je jméno testu, ne závěr

**Titulek pojmenovává, co se měří — a drží se napříč všemi recenzemi stejný.**
„Účinnost podle scénáře", „Náběh teploty v čase", „Hustota energie na kilogram".
Čtenář podle něj graf pozná i po roce a v jiné recenzi.

**Závěr do titulku nepatří.** „Nad 82 % ve všech scénářích" je zjištění — a to má vlastní
místa: **podtitulek** pod nadpisem, **hlavní údaj vpravo** v hlavičce, nebo věta v textu.
Kdyby závěr nesl titulek, každá recenze by měla graf jinak pojmenovaný a nešly by
porovnat.

### Dvě rozvržení hlavičky

| Rozvržení | Kdy | Provedení |
|---|---|---|
| **Na střed** | graf nemá nic než sebe — sada barů, jeden koláč | titulek Display verzálkami na střed, pod ním podtitulek na střed, pod tím data |
| **Vlevo + hlavní údaj vpravo** | z grafu se vytahuje jedno klíčové číslo — peak, průměr, celkem | titulek a podtitulek vlevo, vpravo zarovnaný nahoru **hlavní údaj** (Display, velký) a pod ním jeho popisek verzálkami |

Druhé rozvržení použij, jakmile má graf „to jedno číslo, kvůli kterému tam je" —
divák ho pak přečte, aniž by musel luštit křivku. Míchat obojí v jednom výstupu je
v pořádku; řídí se to obsahem grafu, ne konzistencí layoutu.

Další pravidla — barevné kódování řad, škály, markery, osy — jsou v `charts.md`.

> **Zatím nedodělané.** Kompletní návody na tvorbu grafů včetně ukázek, jak to nedělat,
> se teprve připravují.

---

## 16. Přístupnost

- **Dostatečný kontrast** textu vůči pozadí, zvlášť u tlumených šedých a barevných ploch.
- **Význam nikdy jen barvou.** Doplň tvarem, ikonou nebo popiskem.
- **Čitelné velikosti.** Hierarchie má přednost před zaplněním.
- **Funguje i na malé obrazovce a z dálky** — zásadní pro video a miniatury.
- Na webu a v aplikacích navíc: viditelný focus, klávesová obsluha, textové alternativy,
  respektovat `prefers-reduced-motion`.

---
## 17. Kde co leží

```
design.md              tenhle dokument
motion.md              pohyb — délky, easing, stagger
icons.md               sada ikon a mapování veličina → ikona
charts.md              grafy a datová vizualizace
assets/fonts/          písma (variabilní + statické řezy)
assets/logos/          loga ve všech variantách + CMYK PDF
assets/images/         ikony a obrázky
assets/others/         balíček ikon ke stažení
```

---
# Příloha A — Webová reference

Konkrétní role pro web, ze kterého systém vznikl. Velikost je **× základ**
(`1× = 1,0625 rem ≈ 17 px`). Mimo web ber jen jako příklad.

| Role | × základ | Váha | Řádek | Tracking | Poznámka |
|---|---|---|---|---|---|
| Body / odstavec | 1,00 | 400 | 1,65 | — | lead 1,06× |
| H1 | 2,21 → 3,44 | 800 | 1,08 | −0,015 em | Display, VERZÁLKY, ss02–ss04 |
| Deck (podtitul) | 1,08 → 1,36 | 400 | 1,35 | +0,015 em | tlumená barva |
| H2 | 1,27 → 1,55 | 700 | 1,20 | −0,01 em | ss04 |
| H3 | 1,06 | 700 | 1,25 | — | `--heading-sub` |
| H4 | 1,00 | 700 | 1,30 | — | `--heading-sub` |
| H5 | 0,94 | 700 | 1,30 | — | menší, tlumenější |
| H6 | 0,88 | 700 | 1,35 | +0,04 em | VERZÁLKY, `--muted` |
| Strong | dědí | 700 | | | zvýraznění v textu |
| Code | 0,90 | 400 | | | GeekBoy, ne monospace |
| Citace | 1,56 | 400 | 1,44 | — | kurzíva, linka `--accent` |
| Citace — zdroj | 0,76 | 700 | | +0,04 em | VERZÁLKY, `--accent-text` |
| Nav | 0,88 | 400 | | — | `--muted`, aktivní `--accent-text` |
| Breadcrumb | 0,76 | 400 | | +0,02 em | `--muted` |
| Štítek | 0,71 | 700 | | +0,06 em | VERZÁLKY, plocha `--accent-dim` |
| Meta | 0,82 | 400 | | — | hodnota 700 |
| Tlačítko | 0,88 | 700 | | — | plocha `--accent` |
| Cena | 1,41 | 700 | | −0,02 em | dovětek 0,80× |
| Tabulka — záhlaví | 0,71 | 700 | | +0,06 em | VERZÁLKY, `--accent-text` |
| Tabulka — buňka | 0,88 | 400 | | — | `tnum`, zvýrazněná 700 |
| Hodnocení (score) | 0,88 | 400 | | — | číslo 1,18×, Display |
| Callout — titulek | dědí | 700 | | — | |
| Callout — text | 0,88 | 400 | | — | |
| Hero popisek | 0,76 | 400 | 1,5 | — | `--muted` |
| Brand (název v hlavičce) | — | 700 | | +0,02 em | |
| Poznámka pod čarou | 0,76 | 400 | | — | `--muted` |

Váhy jsou už srovnané na dva řezy — kde web dřív používal 450, 500, 510, 600 nebo 650,
je teď 400 nebo 700.

**Stylistické sady** `ss01`–`ss06` jsou globálně vypnuté a zapínáme je cíleně — H1
(`ss02`–`ss04`), H2 (`ss04`). Nezaměňovat s výchozími featurami písma z kapitoly 5:
tečkovaná nula a čtvercová odrážka nejsou stylistické sady, jsou to výchozí glyfy
a nevypínají se.

---

## A.2 Tvarosloví komponent

Jak vypadají konkrétní stavební prvky. Hodnoty jsou webové, mimo web ber poměry.

| Komponenta | Provedení |
|---|---|
| **Štítek** | pilulka, plocha `--accent-dim`, rámeček z akcentu, text verzálkami |
| **Callout** | diagonální přechod z akcentu, titulek Bold |
| **Citace** | levá linka 3 px v `--accent`, zúžený kurzívní řez |
| **Tabulka** | záhlaví verzálkami v `--accent-text`, řádky oddělené `--border`, hodnoty `tnum` |
| **Score bar** | výplň přechodem z akcentu |
| **Tlačítko** | plné `--accent`, hover `brightness(1.06)` |
| **Spec karta** | hranatá, levá lišta 3 px v barvě stavu — viz kapitola 9 |

Pozadí stránky zatím necháváme čisté. Jemný přechod ani texturu nepoužívej, dokud
nebudou hotové značkové patterny — vlastní řešení by se s nimi pobilo.

