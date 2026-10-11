# Stav projektu geekboy-visual
Aktualizováno: 2026-10-11 (sepsáno z kódu a historie gitu, ne z běhu programu)

## Co dělá
Drží designový systém GeekBoy na jednom místě: pravidla (`design.md` a satelity),
písmo GeekBoy, loga, sadu ikon a barvy. Slouží jako podklad pro tvorbu videí, webu,
aplikací, grafů a merche.

## Co funguje
- Designový systém ve verzi **2.4** (1. 8. 2026): identita, logo, písmo, barvy,
  plochy a karty, pohyb, ikony, grafy, přístupnost.
- Písmo GeekBoy **1.003**: statické řezy, variabilní font a GeekBoy Display ExtraBold
  (OTF, WOFF, WOFF2, TTF).
- Loga ve světlé i tmavé variantě, na šířku i na výšku, plus tiskové CMYK PDF.
- Sada ikon v SVG, rozdělená do tematických skupin.
- Licenční soubor písma `assets/fonts/OFL.txt` (doplněn 2026-10-11).

## Co je rozpracované / nedodělané
- `to-do/otevrene-otazky.md` — odložená rozhodnutí (např. barva pozadí `#000000`
  vs. `#0B0B0B`, role druhé hlavní barvy, doplnění řezů Medium a SemiBold).
- `to-do/vercel-barvy-role-inspirace-geekboy.md` — návrh barev jako rolí, nerozhodnuto.
- `README.md` v sekci Licence ještě píše, že soubor OFL v repu chybí — po doplnění
  `OFL.txt` je ta věta zastaralá.
- Písmo se vyvíjí u zdroje; jestli je verze 1.003 v repu nejnovější, neověřeno.

## Další krok
Neověřeno — v repu není zapsaný. Nabízí se: upravit větu o chybějícím `OFL.txt`
v `README.md` a projít otevřené otázky v `to-do/`.

## Kde co leží
- Pravidla: `design.md` (hlavní), `motion.md`, `icons.md`, `charts.md`
- Historie verzí: `CHANGELOG.md`
- Písmo a licence: `assets/fonts/`
- Loga: `assets/logos/`
- Ikony: `assets/images/`, balíček `assets/others/geekboy-icon-set/`
- Otevřené otázky: `to-do/`
