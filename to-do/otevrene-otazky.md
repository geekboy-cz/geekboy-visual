# Otevřené otázky — co nám chybí definovat

Seznam věcí, které vědomě odkládáme. Každá má návrh řešení, ať se o tom dá rozhodnout
rychle. Když se něco rozhodne, přesune se to do `design.md` a odsud zmizí.

| Stav | Význam |
|---|---|
| 🟠 čeká na Jirku | potřebuje potvrzení od autora identity |
| 🔵 čeká na nás | rozhodneme sami, jen jsme to ještě neudělali |
| ⏳ 2. fáze | Jirka to slíbil dodat |

---

## 🟠 1. Barva pozadí — `#000000`, nebo `#0B0B0B`?

**Kde to vzniklo:** brand manuál ukazuje logo na čistě černé `#000000`, ale zároveň
uvádí `#0B0B0B` (GeekBoy Black) jako jednu ze dvou hlavních barev značky.

**Náš návrh:** `#0B0B0B` je pozadí všech výstupů — webu, videa, aplikací. Čistá černá
`#000000` se používá jen jako podklad pro prezentaci loga a pro tisk. Souvisí to s otázkou 2.

---

## 🟠 2. Jakou roli má druhá signature barva (GeekBoy Black)?

**Kde to vzniklo:** brand manuál má v sekci „Hlavní barvy" dvě barvy — Blue 50 a Black
`#0B0B0B`. Náš dokument doteď pracoval jen s modrou.

**Jak to nejspíš funguje:** není to druhý akcent, který by soutěžil s modrou. Je to
prohlášení, že **tmavý neutrál je součást identity, ne jen pozadí**. GeekBoy se pozná jako
modrá na téhle konkrétní černi — stejně jako se Spotify pozná jako zelená na černé.
Prakticky to znamená, že `#0B0B0B` není zaměnitelné s `#000` ani s `#111`, a že dark mode
je výchozí *proto*, že černá je značková barva — ne z preference.

**Náš návrh:** potvrdit tenhle výklad u Jirky. Pokud platí, vyřeší to i otázku 1.

---

## 🟠 3. Doplnit do brandu Medium (500) a SemiBold (600)?

**Kde to vzniklo:** brand deklaruje jako používané řezy jen Regular 400 a Bold 700.
Náš web a recenze používaly šest vah.

**Co víme:** převedli jsme dvě reálné stránky na dva řezy a změřili rozdíl — 1,47 % plochy
prvního viewportu. Layout drží, nic se nerozsypalo. Ztrácí se jemné odstupňování
v hustých tabulkách, kde 500 a 600 dělaly mezistupeň mezi popiskem a hodnotou.

**Náš návrh:** jet na dvou řezech. Pokud se v tabulkách ukáže, že chybí mezistupeň,
přijít za Jirkou s konkrétní ukázkou, ne s teorií.

---

## 🔵 4. ALL CAPS na H1 u dlouhých českých titulků

**Rozhodnuto:** platí povinně, podle brandu.

**Zbývá ověřit:** jak se chová dlouhý český titulek s diakritikou ve verzálkách na miniatuře
a v prvním snímku videa. Až bude první reálná ukázka, zkontrolovat a případně řešit
délkou textu, ne vypnutím verzálek.

---

## 🔵 5. Zapínat `ss02`–`ss04` i mimo web?

**Kde to vzniklo:** na webu zapínáme alternativní `l`, `r` a bezpatkové `I` na nadpisech.
Ve videu by to znamenalo stejné nastavení v každé kompozici.

**Náš návrh:** zapínat všude, ať je rukopis stejný. Do `design.md` to patří jako jeden
řádek v sekci Písmo, ne jako volba.

---

## ⏳ 6. Patterny (textury)

Jirka připravuje tři směry: halftone pro animované přechody, pevný dotted grid pro velké
plochy, hravý grid pro hlavní YouTube animaci. Do té doby nevymýšlet vlastní vzory.

---

## ⏳ 7. Práce s grafikou — `charts.md`

Jirka slíbil kompletní návody na tvorbu grafů, kombinace barev a řezů včetně ukázek,
jak to nedělat.

**Do té doby napsat vlastní `charts.md`** jako provizorium — jasně ohraničené, ať jde
později vyměnit jedním střihem. Co v něm má být:

- **kódování dat** — velikost a pořadí → délka na společné škále, vývoj v čase →
  vodorovné pořadí, podíl → proporce, práh → vzdálenost od hranice
- **barevné řady** — kdy stavové barvy (ověřeno / výstraha / nejhorší) a kdy neutrální
  odstíny modré; pravidlo, že marker nese barvu své řady
- **osy a škály** — nulová základna u délkových kódování, kdy je v pořádku zúžit rozsah
  a jak to označit (navazuje na *Zjednodušit ano, zkreslit ne* v `design.md`)
- **popisky** — přímé místo legendy, kde jsou lajny na popisky vyhrazené
- **markery** — zaoblený čtvereček jako koncový bod křivky a klíč legendy
- **tabulková čísla** (`tnum`) a jednotky u hodnot
- **typy grafů**, které používáme, a kdy který

Vytáhnout je z čeho — hotové grafy jsou v recenzích nabíječek v `public/`.

---

## 🟠 8. Component Gallery — návrh pro Jirku

**Co bychom chtěli:** jednu stránku se schválenými stavebními kostkami, aby designér
i vývojář viděli, z čeho se GeekBoy skládá. Ne specifikace, jen galerie:

Review Card · Score · CTA · Quote · Timeline · Comparison · Spec Table · Badge · Alert

**Proč:** dnes každý nový výstup znovu vymýšlí, jak vypadá karta s hodnocením.

---

## 🟠 9. Tiskové a barevné systémy

V brand manuálu jsou připravené sloupce Pantone C/U, RAL, NCS a 3M — všechny prázdné.
Pro merch a tisk je budeme potřebovat.

---

## 🔵 10. Jemné váhy v příloze A (webová reference)

Tabulka 25 webových rolí používá váhy 450, 510, 600 a 650. Po rozhodnutí otázky 3
se buď srovná na 400/700, nebo se u ní výslovně napíše, že jde o vědomou odchylku.
