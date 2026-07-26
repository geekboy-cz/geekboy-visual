# Barvy jako role — inspirace z Vercelu pro GeekBoy

## Proč to řešíme

V našem současném `design.md` máme dobře popsanou **fyzickou paletu**:

- hlavní GeekBoy modrou,
- její odstínovou škálu,
- neutrální šedou škálu,
- doplňkové barvy pro významové stavy,
- základní mapování pro light a dark režim.

To je důležitý základ. Dokument říká, **jaké barvy existují a jak vypadají**.

Vercel ale přidává ještě jednu samostatnou vrstvu: barvy nepopisuje primárně podle jejich vzhledu, ale podle jejich **odpovědnosti v rozhraní**.

Neptá se jen:

> Jaká je to barva?

Ale především:

> Jakou roli tato barva v daném místě plní?

Díky tomu nemusí komponenty, stránky ani generované výstupy rozhodovat, jaký konkrétní HEX použít. Rozhodují pouze o významu prvku a design systém tento význam přeloží na správnou barvu.

---

## Základní princip Vercelu

Vercel staví návrh primárně na:

1. hierarchii,
2. typografii,
3. rozestupech,
4. zarovnání,
5. hustotě obsahu.

Barvu přidává až tehdy, když skutečně komunikuje:

- stav,
- akci,
- význam,
- datovou kategorii,
- kontrastní prostředí.

Z jejich pravidel vyplývá:

- výchozí návrh má fungovat monochromaticky,
- barva nemá opravovat slabou hierarchii,
- pozitivní informace automaticky neznamená zelenou,
- barevný povrch nebo rámeček musí mít důvod,
- význam nesmí být komunikován pouze barvou.

Barva tedy není dekorace. Je to informační vrstva.

---

# Dvě úrovně barev

## 1. Fyzická paleta

Fyzický token popisuje, **jak barva vypadá**.

Například:

```css
--blue-50
--gray-100
--gray-20
--red-50
```

Tento typ systému už v GeekBoy `design.md` máme.

Je užitečný pro:

- správu odstínů,
- tvorbu light a dark tématu,
- definování kontrastu,
- grafické výstupy,
- technickou implementaci.

Fyzická paleta ale sama neříká, kdy a proč má být určitý odstín použit.

---

## 2. Sémantické role

Sémantický token popisuje, **co barva dělá**.

Například:

```css
--surface-primary
--text-secondary
--border-subtle
--color-error
```

Komponenta potom nepoužívá přímo:

```css
background: #0B0B0B;
color: #D4D4D4;
```

ale:

```css
background: var(--surface-primary);
color: var(--text-primary);
```

Tím se oddělí:

```text
význam prvku
od
konkrétního odstínu
```

Paleta se může změnit, ale význam komponenty zůstává stejný.

---

# Jaké role používá Vercel

Vercel rozděluje veřejné barevné tokeny do několika rodin.

## 1. Povrchy

```css
--vbg-surface-primary
--vbg-surface-secondary
--vbg-surface-contrast
```

### `surface-primary`

Hlavní plátno výstupu.

Použití:

- pozadí stránky,
- hlavní plocha reportu,
- základní prostředí aplikace nebo dokumentu.

Komponenta ví pouze:

> Jsem umístěná na hlavním povrchu.

Neví, zda jde v daném tématu o bílou, černou nebo jinou neutrální barvu.

### `surface-secondary`

Vedlejší nebo lehce oddělená plocha.

Použití může zahrnovat:

- vstupní pole,
- pomocný blok,
- sekundární kontext,
- skutečně samostatnou skupinu obsahu.

Neznamená automaticky „karta“.

Vercel současně zdůrazňuje, že se plocha nemá používat jen proto, že designer potřebuje něco vizuálně oddělit. Nejprve se má zkusit spacing, zarovnání, typografie nebo změna hustoty.

### `surface-contrast`

Výrazně kontrastní prostředí.

Například:

- tmavý pás ve světlé stránce,
- světlá sekce uvnitř tmavého výstupu,
- zásadní blok, který oprávněně mění celé vizuální prostředí.

Důležitá myšlenka:

> Změna povrchu není jen změna backgroundu.

Kontrastní povrch musí mít vlastní správně navázané role pro text, rámečky, ovládací prvky a stavy.

---

## 2. Text

```css
--vbg-text-primary
--vbg-text-secondary
--vbg-text-on-contrast
--vbg-text-on-contrast-secondary
```

### `text-primary`

Hlavní kontrastní úroveň textu.

Použití:

- nadpisy,
- běžný obsah,
- hlavní hodnoty,
- důležité názvy,
- klíčové výsledky.

Neznamená jednu konkrétní typografickou úroveň. H1, odstavec i velká číselná hodnota mohou používat stejnou barevnou roli a hierarchii vytvářet velikostí, vahou a umístěním.

### `text-secondary`

Podřízená textová úroveň.

Použití:

- metadata,
- captions,
- zdroje,
- pomocný text,
- doplňující vysvětlení,
- méně důležité popisky.

Jeho úloha je:

> Zůstat čitelný, ale nesoutěžit s hlavním sdělením.

### `text-on-contrast`

Hlavní text na kontrastním povrchu.

Místo ručního použití `white` nebo `black` komponenta deklaruje:

> Jsem hlavní text uvnitř kontrastního prostředí.

### `text-on-contrast-secondary`

Sekundární text na kontrastním povrchu.

Vznikají tak dvě paralelní hierarchie:

```text
Běžný povrch:
- text-primary
- text-secondary

Kontrastní povrch:
- text-on-contrast
- text-on-contrast-secondary
```

---

## 3. Rámečky a hranice

```css
--vbg-border-subtle
--vbg-border-default
--vbg-border-strong
--vbg-border-on-contrast
--vbg-focus
```

### `border-subtle`

Nejméně výrazné oddělení.

Použití:

- jemné linky v tabulce,
- sekundární separátory,
- nenápadné členění,
- lehký outline.

Nemá vytvářet hlavní hierarchii.

### `border-default`

Standardní hranice.

Použití:

- inputy,
- běžné ovládací prvky,
- jasnější oddělení,
- základní outline interaktivních prvků.

### `border-strong`

Výrazná hranice.

Použití:

- aktivní oblast,
- důležité oddělení,
- vybraný prvek,
- situace, kdy hranice musí být okamžitě patrná.

Kdyby se používala všude, přestává být „strong“.

### `border-on-contrast`

Hranice určená pro kontrastní prostředí.

Stejně jako text potřebuje vlastní kontrastní variantu, potřebuje ji i border. Běžná hranice by mohla na tmavém nebo světlém kontrastním poli zaniknout.

### `focus`

Samostatná role pro focus stav.

Focus není jen další border. Komunikuje konkrétní význam:

> Tento prvek právě ovládá uživatel klávesnicí.

Vizuálně podobné prvky tedy nemusí sdílet token, pokud mají jinou odpovědnost.

---

## 4. Stavové barvy

```css
--vbg-color-info
--vbg-color-success
--vbg-color-warning
--vbg-color-error
```

Tyto role nepopisují obecně „modrou, zelenou, oranžovou a červenou“. Popisují konkrétní stav.

### `info`

Neutrální informační stav.

Použití:

- systémová poznámka,
- vysvětlení,
- doplňující fakt,
- stav bez pozitivního či negativního výsledku.

Nemá být používán jen jako obecná dekorativní modrá.

### `success`

Skutečně úspěšně dokončený nebo platný stav.

Například:

- akce byla dokončena,
- data byla uložena,
- kontrola prošla,
- systém funguje,
- test splnil podmínku.

Důležité rozlišení:

```text
Doporučený produkt
není automaticky
success stav
```

To, že je něco pozitivní, ještě neznamená, že má být zelené.

### `warning`

Situace vyžadující pozornost.

Například:

- blížící se limit,
- důležitá podmínka,
- možné riziko,
- stav, který ještě není chybou.

### `error`

Skutečná chyba nebo blokující stav.

Například:

- akce selhala,
- hodnota je neplatná,
- výpočet nelze dokončit,
- systém není dostupný.

Pokud se stejná červená používá pro chybu, běžnou nevýhodu produktu, slabé skóre i dekoraci, ztrácí informační sílu.

---

## 5. Datové série

```css
--vbg-chart-1
--vbg-chart-2
--vbg-chart-3
--vbg-chart-4
--vbg-chart-5
--vbg-chart-6
```

Tyto role jsou určeny pro rozlišení datových sérií.

Například v jednom grafu:

```text
chart-1 = GeekBoy měření
chart-2 = výrobce
chart-3 = konkurence
```

V jiném grafu mohou stejné role reprezentovat jiné série.

Nejsou to stavové barvy.

To znamená, že není vhodné automaticky mapovat:

```text
nejlepší výsledek = success
nejhorší výsledek = error
```

Pokud barva pouze odlišuje dvě značky nebo série, má používat datovou roli. Stavovou barvu má dostat jen tehdy, když skutečně komunikuje stav nebo význam.

---

# Jak role spolupracují v komponentě

Příklad běžného výsledkového panelu:

```text
Pozadí:
surface-secondary

Hlavní hodnota:
text-primary

Vysvětlení:
text-secondary

Jemné oddělení:
border-subtle

Chybový stav:
color-error

Klávesnicový focus:
focus
```

Komponenta je popsána významem, nikoli odstíny.

V light a dark tématu se mohou konkrétní hodnoty změnit, ale struktura role zůstává stejná.

---

# Co už GeekBoy má

Současný `design.md` už obsahuje dobrou fyzickou základnu:

## Brandová paleta

- jediná hlavní modrá `#1148E6`,
- odvozená modrá škála,
- zákaz zavádění další „skoro stejné“ modré.

## Neutrály

- samostatná šedá škála,
- odstíny pro pozadí, text, plochy a linky.

## Významové akcenty

- cyan pro klíčové informace,
- green pro dobré nebo ověřené,
- red pro špatné,
- orange pro výstrahu.

## Light a dark princip

- brand a významové barvy zůstávají,
- mění se především neutrální povrchy a text.

## Základní sémantické tokeny pro web

V příloze už existují role jako:

```css
--bg
--surface
--border
--text
--muted
--accent
--accent-text
--key
--good
--bad
--warn-b
```

To znamená, že GeekBoy už část sémantické vrstvy má. Není ale zatím popsaná jako plnohodnotný systém použitelný napříč webem, videem, grafikou a aplikacemi.

---

# Co nám proti přístupu Vercelu chybí

## 1. Jasné oddělení fyzické palety a sémantických rolí

V současném dokumentu jsou vedle sebe:

- konkrétní odstíny,
- významové barvy,
- základní role.

Není ale explicitně vysvětleno:

```text
Palette token = jak barva vypadá
Semantic token = jakou má odpovědnost
```

Tohle by mělo být základní pravidlo systému.

---

## 2. Kompletní rodina povrchů

Aktuálně máme především:

```css
--bg
--surface
```

Chybí přesnější rozhodnutí, zda chceme rozlišovat například:

```css
--surface-primary
--surface-secondary
--surface-elevated
--surface-contrast
--surface-brand
```

Nemusíme převzít všechny. Potřebujeme ale vědět, kolik různých prostředí skutečně používáme a která mají vlastní význam.

---

## 3. Přesnější textová hierarchie

Aktuálně máme:

```css
--text
--muted
--accent-text
```

Mohlo by být užitečné zvážit:

```css
--text-primary
--text-secondary
--text-tertiary
--text-on-brand
--text-on-brand-secondary
--text-on-contrast
```

Klíčová otázka není počet tokenů, ale zda se v našich výstupech opakují jasně odlišné textové odpovědnosti.

---

## 4. Více úrovní hranic

Aktuálně máme obecný:

```css
--border
```

Chybí rozhodnutí, zda potřebujeme:

```css
--border-subtle
--border-default
--border-strong
--border-on-brand
--focus
```

To by pomohlo zejména u:

- aplikací,
- formulářů,
- tabulek,
- grafů,
- interaktivních Remotion vizualizací,
- komponent s více úrovněmi hierarchie.

---

## 5. Oddělený focus token

Focus je interakční a přístupnostní stav. Neměl by být pouze silnější border nebo brandová barva použitá ad hoc.

Samostatný token zaručí:

- konzistenci,
- viditelnost,
- správnou funkci v light a dark režimu,
- přístupnost.

---

## 6. Přesnější definice stavových barev

Naše současné názvy jsou zčásti obsahové:

```text
dobře / ověřeno
špatně / nejhorší
klíčové / nej
výstraha
```

To je vhodné pro recenzní a datový obsah, ale může se míchat se systémovými stavy.

Například:

```text
Produkt má špatnou výdrž
není totéž jako
Formulář obsahuje chybu
```

Můžeme proto potřebovat rozlišit:

```css
--state-success
--state-warning
--state-error
--state-info
```

od obsahových rolí:

```css
--verdict-good
--verdict-bad
--highlight-key
```

Nebo vědomě rozhodnout, že je chceme slučovat. Důležité je, aby to bylo explicitní.

---

## 7. Samostatné role pro datové série

V našem dokumentu zatím není jasně definovaný systém typu:

```css
--chart-1
--chart-2
--chart-3
```

Pro GeekBoy jsou grafy a srovnání důležitou součástí identity. Proto potřebujeme rozhodnout:

- jak se rozlišují série,
- kdy je série neutrální,
- kdy je zvýrazněná brandem,
- kdy se používá sémantická barva,
- zda GeekBoy měření má stabilní barvu,
- zda konkurenti mají stabilní nebo pořadové role.

---

## 8. Pravidlo, že komponenty nesahají přímo na paletu

Na webu už dokument doporučuje používat tokeny namísto HEX hodnot. Stejný princip by bylo dobré rozšířit obecně:

```text
Komponenta nesahá přímo na blue-50 nebo gray-80,
pokud existuje sémantická role.
```

Například:

```css
/* Nevhodné */
.card {
  background: var(--gray-90);
}

/* Vhodné */
.card {
  background: var(--surface-secondary);
}
```

Přímé použití fyzické palety může zůstat povolené pro:

- ilustrace,
- specifické datové vizualizace,
- generování gradientu nebo škály,
- výjimečné grafické výstupy.

Ale nemělo by být defaultem komponent.

---

## 9. Pravidla pro barvu jako rozhodovací nástroj

V našem dokumentu by se hodilo explicitně uvést:

- nejprve vytvoř hierarchii typografií a prostorem,
- barvu nepoužívej jako náplast na nejasný layout,
- plocha a rámeček musí mít informační důvod,
- pozitivní informace automaticky neznamená zelenou,
- negativní parametr automaticky neznamená systémovou červenou,
- význam nikdy nekomunikuj pouze barvou,
- návrh by měl zůstat pochopitelný i v odstínech šedi.

---

# Otázky pro společné doladění s designérem

## Povrchy

- Kolik skutečně potřebujeme úrovní povrchu?
- Potřebujeme zvlášť elevated, contrast a brand surface?
- Kdy je oprávněné použít barevnou plochu místo spacingu?

## Text

- Stačí nám primary a secondary?
- Máme samostatnou roli pro metadata?
- Potřebujeme vlastní text na brandové modré?
- Jak se chová text na kontrastním povrchu?

## Borders

- Potřebujeme subtle, default a strong?
- Jak bude vypadat focus?
- Kdy se border nepoužívá vůbec?

## Stavy a verdikty

- Je „dobrý produkt“ stejná role jako „úspěšná akce“?
- Je „špatná vlastnost“ stejná role jako „systémová chyba“?
- Potřebujeme oddělit UI stavy od redakčních verdiktů?

## Grafy

- Má mít GeekBoy vlastní stabilní datovou barvu?
- Jak se odlišují ostatní série?
- Kdy použít brand a kdy neutrální škálu?
- Kdy je legitimní použít red, green nebo orange v grafu?
- Jak zajistit, aby graf fungoval i bez barvy?

## Implementace

- Budou stejné sémantické názvy použity ve Figmě, CSS, Remotionu a aplikaci?
- Kde bude jediný source of truth?
- Které tokeny jsou veřejné a které pouze interní?
- Smějí si jednotlivé projekty vytvářet vlastní role?

---

# Možný směr systému

Ne jako hotové rozhodnutí, ale jako diskusní základ:

```css
/* Povrchy */
--surface-primary
--surface-secondary
--surface-elevated
--surface-contrast
--surface-brand

/* Text */
--text-primary
--text-secondary
--text-tertiary
--text-on-brand
--text-on-brand-secondary
--text-on-contrast

/* Hranice a interakce */
--border-subtle
--border-default
--border-strong
--border-on-contrast
--focus

/* Akce */
--action-primary
--action-primary-hover

/* UI stavy */
--state-info
--state-success
--state-warning
--state-error

/* Redakční a obsahové role */
--highlight-key
--verdict-good
--verdict-bad
--verdict-warning

/* Data */
--chart-1
--chart-2
--chart-3
--chart-4
--chart-5
--chart-6
```

Nemusíme mít všechny. Smyslem je nejprve pojmenovat opakující se odpovědnosti a až potom je mapovat na konkrétní GeekBoy barvy.

---

# Hlavní ponaučení

Vercel nevytváří barevný token podle otázky:

> Jakou barvu bych tady chtěl?

Vytváří ho podle otázky:

> Jakou odpovědnost má tato barva v rozhraní?

GeekBoy už má silnou paletu a základní sémantické tokeny. Dalším krokem není nutně přidávat více odstínů. Je jím přesněji popsat:

- které role existují,
- co znamenají,
- kdy se používají,
- které role se nesmí zaměňovat,
- jak se překládají mezi webem, videem, aplikací a grafikou.
