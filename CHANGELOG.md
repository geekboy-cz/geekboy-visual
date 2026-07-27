# Changelog

Historie designového systému GeekBoy. Verze odpovídá poli `version` v hlavičce
`design.md` — podle něj se pozná, jestli je tvoje kopie aktuální.

---

## 2.2 — 27. 7. 2026

Vzniklo z převodu recenze nabíječky na 2.1. Všechny tři změny jsou **zpětné kroky** —
2.1 přidala volnost, kterou generátor zneužil k přidělávání prvků navíc.

**Opraveno**

- **Rozvržení hlavičky grafu — zpátky na jedno.** 2.1 zavedla druhou variantu *„vlevo
  + hlavní údaj vpravo"*. V praxi se přidělávala i tam, kde nebyla potřeba, a vyráběla
  zbytečné dvojice typu *„85,5 % / PRŮMĚR NAPŘÍČ SCÉNÁŘI"* nad grafem, který tutéž
  hodnotu sám ukazuje. **Platí jedna podoba: titulek a podtitulek na střed.** Vytažené
  číslo a další varianty přijdou jako hotová šablona.
- **Legenda u spojnicových grafů je výchozí, ne výjimka.** Pravidlo *„přímý popisek
  místo legendy, kdykoli to jde"* platilo plošně, takže z grafů s křivkami legendy
  zmizely úplně a popisky skončily naházené v datové ploše. Nově rozhoduje **tvar
  řady**: bary, plochy a siluety popisek u tvaru — **křivky a referenční čáry legendu**.
- **Odznak je plný, ne tlumený.** Příloha A předepisovala u štítku plochu `--accent-dim`
  s textem v `--accent-text`, tedy modrou na modré — nemá kontrast a splývá. Odznak má
  **sytou výplň `--accent` a bílý text** (referenční provedení *Druhé místo* z Jirkovy
  palety). Doplněna kapitola *Odznak je plný, ne tlumený* do kapitoly 9, která staví
  odznak proti velké ploše: čím menší prvek, tím sytější barva.
  `--accent-dim` zůstává pro callouty a zvýrazněné plochy.
- **Rámeček plochy grafu v dark z Gray 90 na Gray 80.** `--chart-bg` je Gray 100, což je
  přesně pozadí stránky — na Gray 90 měla linka kontrast 1,1 : 1 a graf splýval s textem,
  tedy přesně to, čemu má plocha zabránit. Otevřený bod z revize 2.1, teď uzavřený.

**Doplněno do *Takhle to nedělej***

- Odznak s tlumenou plochou a textem téže barvy.
- Vytažený hlavní údaj vedle nadpisu grafu, který opakuje hodnotu z grafu.
- Spojnicový graf bez legendy s popisky v datové ploše.

## 2.1 — 27. 7. 2026

Vzniklo z převodu reálné recenze na verzi 2.0. Většinu doplňků vynutila Jirkova ukázka
`Barevná paleta · Akcenty — GeekBoy.html`, ve které jsou vzory, co v dokumentu chyběly.

**Opraveno**

- **Titulek grafu.** Dřív *„říká, co je vidět, ne jak se graf jmenuje"*. Teď obráceně:
  titulek je stabilní jméno testu, závěr patří do podtitulku nebo do hlavního údaje.
  Původní pravidlo dávalo každé recenzi jiný název téhož grafu.
- **Šedá pro konkurenci v grafech** — z Gray 40–60 na **Gray 70 v dark, Gray 30 v light**.
  Střední šedá působila jako druhá plnohodnotná řada.
- **„Tmavý zaoblený obdélník kolem každého grafu"** v seznamu *Takhle to nedělej* nově
  míří jen na video a statickou grafiku. **Na webu má graf vlastní plochu** — jinak
  splyne s textem.
- **Kdy smí číslo dostat stavovou barvu.** Dřívější dělení „stav vs. názor" bylo
  nepoužitelné: zakazovalo obarvit +23 % nad deklarovaným limitem, což je měření proti
  referenci. Nové kritérium je **práh nebo referenční hodnota**, a výslovně pokrývá
  i směr změny (zlevnění, zlepšení výkonu).

**Přidáno**

- **Jak stavovou barvu složit** — plocha je *tmavá varianta téhož odstínu*, text a tečka
  `primary`, rámeček 40–50 % mix. Chybějící recept byl důvod, proč stavové chipy
  vycházely jako barevný rámeček kolem šedé plochy.
- **Dva tvary stavu** — s plochou a inline bez plochy (tučný barevný text + tečka
  s prstencem). Neutrální stav (*offline*, *neměřeno*) je `--muted`, ne červená.
- **Barevná plocha se míchá do podkladu** — `primary` není podklad. 8–18 % barvy do
  podkladu, nebo tmavá varianta odstínu. Sytá výplň jen na malý odznak.
- **Plocha grafu** — konkrétní hodnoty: Gray 100 podklad, Gray 90 linka, zaoblení 16 px
  (vědomá výjimka z 12px karet).
- **Dvě rozvržení hlavičky grafu** — na střed u samostatné sady barů, vlevo + hlavní
  údaj vpravo tam, kde se z grafu vytahuje jedno číslo.

- **Legenda** — kdy je legenda správná volba (referenční čára přes celou šířku, tři a víc
  řad, kolidující popisky), rozměry (text 11,5 px Bold, mezery 6 a 14 px) a hlavně
  pravidlo, že **klíč napodobuje tvar své řady**: u křivky úsečka 14 × 3 px (u přerušované
  řady přerušovaná stejným rytmem), u plošné řady zaoblený čtvereček 12–14 px.

**Opraveno — spec karty**

- Kritérium *„karty, které nesou naměřený parametr se stavem"* bylo příliš široké — sedí
  skoro na cokoli v laboratorní recenzi a vede k tomu, že se zhranatí i věci, které mají
  být zaoblené. Nahrazeno rozlišením **spec karta vs. datová dlaždice** a jedinou
  rozhodovací otázkou: *čtou se položky proti sobě, nebo každá zvlášť?*
- Doplněna **datová dlaždice** jako vlastní komponenta (zaoblená 12 px, plocha podle
  pásma, číslo na střed) — dřív v dokumentu nebyla, takže neexistoval správný tvar
  pro sadu teplot, spotřeb nebo hodnot téhož parametru.
- Doplněna poznámka, že u pěti a víc hodnot na společné škále má přednost **graf**
  před mřížkou dlaždic.

**Opraveno — klíč legendy**

- `charts.md` říkal *„klíč v legendě = zaoblený čtvereček místo tečky nebo čárky"* plošně.
  U spojnicové řady je to špatně: plný 13px čtverec vedle tenké přerušované čáry váží
  opticky víc než data, která popisuje. Zaoblený čtvereček zůstává klíčem u **plošných**
  řad a koncovým bodem křivky.

**Otevřené**

- Zaoblení konce baru — dokument říká rovné, Jirkova paleta má `0 4px 4px 0`.
  Viz `charts.md` kapitola 8.

## 2.0 — 26. 7. 2026

Sjednocení brandového manuálu od Jirky Chlébuse s naším designovým systémem do jednoho
dokumentu.

**Opraveno**

- Název písma a cesty k souborům.
- Hodnoty modré škály Blue 40 až Blue 10 — dřívější odstíny neodpovídaly brandu.
- Náhradní písmo: Arial (Windows), Helvetica / San Francisco (Mac), Hubot Sans
  ve sdílených online dokumentech.
- Řezy omezeny na Regular 400, Bold 700 a GeekBoy Display ExtraBold 800.
  Kde web dřív používal 450, 500, 510, 600 nebo 650, je teď 400 nebo 700.

**Odebráno**

- Barva cyan `#00B7FF` — nepoužíváme.

**Přidáno**

- Ekosystém: GeekBoy, Lab, Extra, Web, Discord, sociální sítě.
- Idea vizuálního stylu — zaoblený čtverec jako signaturní tvar.
- Logo: varianty a jejich použití, minimální velikosti, ochranná zóna, zákazy, cesty
  k souborům.
- Ikony: barevná pravidla a poznámka o přebarvování.
- OpenType featury a technikálie variabilního fontu — osy, výchozí instance, kurzíva.
- Pořadí priorit pro situace, kdy si požadavky odporují.
- Kapitoly *Plochy, karty a prostor*, *Takhle to nedělej*
  a *Kdy je v pořádku pravidla porušit*.

**Odloženo** — viz `otevrene-otazky.md`

- Barva pozadí `#000000` versus `#0B0B0B`.
- Role druhé signature barvy (GeekBoy Black).
- Případné doplnění řezů Medium a SemiBold.

---

## 1.0 — červen 2026

První verze designového systému.
