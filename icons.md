---
name: geekboy-icons
description: >
  Použij, když sázíš ikonu do jakéhokoli výstupu GeekBoy — spec karty, grafy, tabulky
  parametrů, video, web. Obsahuje kompletní sadu, mapování veličina → ikona,
  barevná pravidla a způsob přebarvování.
version: 1.0
updated: 2026-07-26
---

# GeekBoy — ikony

Doplněk k `design.md`, kapitola 14. Tady je kompletní sada a pravidla použití.

**253 ikon.** Jde o open-source sadu **[Lucide](https://lucide.dev/icons/)**, převedenou
na plochy — obrysy jsou vektorizované na výplně, takže se dají přebarvovat.
Ikony `research`, `fps`, `dollar`, `adobe-rgb` a `gamepad-directional` jsou vlastní.

Lucide má i [animované verze](https://lucide-animated.com/), pokud potřebuješ ikonu rozhýbat.

---

## Pravidla

### Barvy

| Režim | Ikona | Text u ní |
|---|---|---|
| **Dark** — výchozí | Blue 40 `#3873FF` | Gray 10 `#D4D4D4` |
| **Light** — jen na velmi světlé scény | Blue 50 `#1148E6` | Gray 100 `#0B0B0B` |

Ve stavovém kontextu — ověřeno, výstraha, nejhorší — nese ikona barvu stavu, ne modrou.
Jinde modrá zůstává.

### Kdy ikonu vůbec použít

Ikona má smysl, když **znatelně zrychlí rozpoznání** — kategorie parametru ve specifikaci,
stav, typ konektoru, druh měření. Jinak dej přednost textovému popisku; slovo je
jednoznačnější než piktogram.

Zaoblený čtverec jako podklad pod ikonou je v pořádku tam, kde ikona něco **označuje**.
Není v pořádku jako barevná dlaždice, která zaplňuje místo. Test: kdybys ikonu odebral,
přijdeš o informaci?

Nemíchej styly. Všechny ikony pocházejí z jedné sady — nedoplňuj je piktogramy odjinud
ani emoji.

### Velikosti

Ikona se řídí velikostí textu, u kterého stojí. Výchozí poměr je **1× až 1,25×** výšky
řádku sousedního textu — v běžném textu tedy zhruba 16–20 px, u nadpisu odpovídajícím
násobkem.

Optické zarovnání má přednost před matematickým: ikona vedle textu se zarovnává
na střed písmene, ne na účaří.

---

## Přebarvování — pozor

Kořenový `<svg>` sice deklaruje `stroke="currentColor"`, ale **všechny cesty mají ve stylu
natvrdo `fill:#000000`**. Barva zvenčí se proto neprojeví a na tmavém pozadí je ikona
neviditelná.

Dvě funkční cesty:

**CSS maska** — nejrychlejší, nevyžaduje úpravu souborů:

```tsx
export const Icon = ({ name, size = 24, color = "var(--accent-text)" }) => (
  <span style={{
    display: "inline-block", width: size, height: size, background: color,
    WebkitMaskImage: `url(/icons/${name}.svg)`, maskImage: `url(/icons/${name}.svg)`,
    WebkitMaskSize: "contain", maskSize: "contain",
    WebkitMaskRepeat: "no-repeat", maskRepeat: "no-repeat",
  }}/>
);
```

**Odstranit fill při buildu** — pokud potřebuješ ikony inline v SVG kompozici, nahraď
`fill:#000000` za `fill:currentColor`. Pak fungují normálně.

**Rozměry:** `viewBox 24 × 24`, exportované na 1024 × 1024 px. Škáluj přes `width`
a `height`, ne přes `transform`.

---

## Mapování — od veličiny k ikoně

Tohle je naše, ne z brandu. Vzniklo z toho, co reálně měříme, a mělo by držet napříč
recenzemi — aby stejná veličina měla vždy stejnou ikonu.

| Veličina | Ikona |
|---|---|
| výdrž na baterii | `battery-full` · stavy `battery-low` / `battery-medium` |
| nabíjení, rychlost nabíjení | `battery-charging` · `plug-zap` |
| příkon, spotřeba | `power` · `zap` |
| doba, latence, odezva | `gauge` · `clock-4` |
| hmotnost | `weight` · `scale` |
| rozměry | `ruler` |
| konstrukce, odolnost | `dumbbell` |
| teplota, zahřívání | `thermometer` · `thermometer-sun` · `flame` |
| chlazení, hlučnost ventilátoru | `fan` · `wind` |
| jas, kontrast | `sun` · `contrast` |
| barevný gamut, kalibrace | `palette` · `swatch-book` · `adobe-rgb` |
| obnovovací frekvence | `refresh-ccw` · `fps` |
| rozlišení, velikost displeje | `monitor` · `zoom-in` |
| hlasitost, zvuk | `volume-2` · `audio-lines` |
| mikrofon | `mic` |
| sluchátka | `headphones` · `headset` |
| konektory, porty | `cable` · `hdmi-port` · `card-sim` |
| bezdrát, dosah | `wifi` · `bluetooth` · `signal` |
| výkon procesoru | `cpu` |
| paměť, úložiště | `memory-stick` · `hard-drive` |
| cena, poměr cena/výkon | `wallet` · `dollar` |
| verdikt, doporučení | `trophy` · `award` · `crown` |
| ověřeno měřením | `search-check` · `circle-check-big` |
| výstraha, kompromis | `triangle-alert` |
| chybí, nepodporováno | `x` · `ban` |
| metodika, laboratorní test | `flask-conical` · `research` |
| trend nahoru / dolů | `trending-up` · `trending-down` |
| srovnání | `chart-no-axes-combined` · `arrow-right-left` |

Když měříš něco, co v tabulce není, přiřaď ikonu jednou a **dopiš ji sem** — jinak
se pro tutéž veličinu časem objeví tři různé.

---

## Sada podle skupin

Rozdělení je z brandového manuálu. Deset ikon patří do dvou skupin zároveň
(`power`, `sun`, `gauge`, `monitor`, `sliders-vertical`, `headphone-off`, `headphones`,
`speaker`, `gamepad-2`, `scan-qr-code`), takže součet položek je 263, ale souborů je 253.

Soubory: `assets/images/<název>.svg` · kompletní balíček `assets/others/geekboy-icon-set.zip`

### Výdrž a napájení (13)
`battery` · `battery-low` · `battery-medium` · `battery-full` · `battery-charging` ·
`clock-4` · `clock-fading` · `hourglass` · `plug` · `plug-zap` · `unplug` · `power` ·
`smartphone-charging`

### Konstrukce (4)
`dumbbell` · `ruler` · `scale` · `weight`

### Teploty (8)
`sun` · `snowflake` · `thermometer` · `thermometer-sun` · `fan` · `flame` · `wind` ·
`air-vent`

### Displej (18)
`contrast` · `crosshair` · `eye` · `gauge` · `fps` · `monitor` · `monitor-smartphone` ·
`palette` · `refresh-ccw` · `sliders-horizontal` · `sliders-vertical` · `swatch-book` ·
`app-window` · `zap` · `zoom-in` · `zoom-out` · `sun` · `adobe-rgb`

### Audio (12)
`headphone-off` · `headphones` · `headset` · `mic` · `music` · `radio` · `speaker` ·
`volume-1` · `volume-2` · `volume-off` · `volume-x` · `audio-lines`

### Hardware (32)
`monitor` · `laptop` · `projector` · `server` · `hard-drive` · `smartphone` ·
`memory-stick` · `cpu` · `circuit-board` · `gamepad-2` · `pencil` · `calculator` ·
`camera` · `camera-off` · `fingerprint-pattern` · `key-square` · `lock-keyhole` ·
`lock-keyhole-open` · `printer` · `shield` · `shield-cog-corner` · `shield-off` ·
`webcam-off` · `webcam` · `sliders-vertical` · `card-sim` · `headphone-off` ·
`headphones` · `rectangle-goggles` · `settings-2` · `video-off` · `video`

### Konektivita (25)
`airplay` · `at-sign` · `bluetooth` · `bluetooth-off` · `cable` · `link-2` ·
`message-circle` · `message-circle-off` · `message-square-more` · `messages-square` ·
`network` · `nfc` · `phone` · `phone-call` · `router` · `wifi-off` · `wifi` · `wifi-cog` ·
`power-off` · `power` · `hdmi-port` · `signal` · `smartphone-nfc` · `speaker` · `speech`

### Hodnocení (27)
`check` · `x` · `circle-check-big` · `angry` · `laugh` · `square-check-big` · `star` ·
`star-half` · `thumbs-up` · `thumbs-down` · `award` · `gem` · `ban` · `biceps-flexed` ·
`bookmark` · `chess-king` · `chess-queen` · `crown` · `dollar` · `heart` · `medal` ·
`party-popper` · `receipt-text` · `trophy` · `user-star` · `wallet` · `triangle-alert`

### Grafy a trendy (32)
`trending-up` · `trending-down` · `trending-up-down` · `chart-down` · `chart-up` ·
`chart-line` · `chart-bar-decreasing` · `chart-column-decreasing` · `chart-bar` ·
`chart-column-increasing` · `chart-no-axes-column-increasing` · `chart-no-axes-combined` ·
`chart-candlestick` · `chart-pie` · `arrow-up` · `arrow-down` · `arrow-left` ·
`arrow-right` · `arrow-up-left` · `arrow-up-right` · `arrow-down-left` ·
`arrow-down-right` · `arrow-right-left` · `arrow-up-down` · `square-arrow-up` ·
`square-arrow-down` · `square-arrow-left` · `square-arrow-right` ·
`square-arrow-down-left` · `square-arrow-down-right` · `square-arrow-up-left` ·
`square-arrow-up-right`

### Ovládání a navigace (40)
`corner-left-down` · `corner-left-up` · `corner-right-down` · `corner-right-up` ·
`corner-up-left` · `corner-up-right` · `corner-down-left` · `corner-down-right` ·
`funnel` · `scan-qr-code` · `locate-fixed` · `map-pin` · `map-pin-check-inside` ·
`map-pinned` · `mouse-pointer` · `navigation` · `pen-tool` · `pin` · `plus` · `pointer` ·
`hand-metal` · `shopping-cart` · `gamepad-directional` · `gamepad-2` · `keyboard` ·
`mouse` · `mouse-off` · `move-diagonal-2` · `move-up-left` · `move-down-right` ·
`move-diagonal` · `move-up-right` · `move-down-left` · `move-horizontal` · `move-left` ·
`move-right` · `move-up` · `move-down` · `move-vertical` · `move`

### Systém a soubory (13)
`book-marked` · `database-search` · `download` · `earth` · `folder` · `folder-open` ·
`history` · `list-todo` · `rotate-cw` · `save` · `square-pen` · `sticky-notes` · `trash-2`

### Informace (8)
`lightbulb` · `circle-question-mark` · `search-alert` · `info` · `search` · `search-code` ·
`search-x` · `search-check`

### Servis a testování (31)
`bell` · `bell-ring` · `bug` · `bug-off` · `cog` · `flask-conical-off` · `flask-conical` ·
`research` · `gauge` · `leaf` · `play` · `pause` · `radar` · `recycle` · `scan-eye` ·
`scan-face` · `scan-search` · `scan-qr-code` · `scan-text` · `scan` · `slice` · `scissors` ·
`settings` · `skull` · `sparkle` · `sparkles` · `stamp` · `user` · `wrench` · `wrench-off` ·
`target`
