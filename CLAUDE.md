# CLAUDE.md

Pravidla pro AI agenty pracující na tomhle repozitáři.
**Před prací si přečti `README.md`** a u změn pravidel příslušnou kapitolu `design.md`.

## Co to je

Designový systém GeekBoy: písmo, loga, ikony, barvy a pravidla, jak z nich stavět
videa, web, aplikace, grafy a merch. Není to program — žádný kód, build ani instalace.

## Jak je postavený

- `design.md` — hlavní dokument, všechny hodnoty. Verze je v hlavičce (pole `version`).
- `motion.md`, `icons.md`, `charts.md` — detaily k jednotlivým disciplínám.
- `CHANGELOG.md` — historie verzí systému.
- `assets/fonts/` — písmo GeekBoy (statické řezy, variabilní font, Display) a `OFL.txt`.
- `assets/logos/` — loga (SVG) a tiskové CMYK PDF.
- `assets/images/` — ikony (SVG), `assets/others/` — balíček ikon ke stažení.
- `to-do/` — otevřené otázky a nerozhodnuté návrhy.

## Na co dát pozor

- **Změna pravidla = nová verze.** Zvyš `version` a `updated` v hlavičce `design.md`,
  zapiš změnu do `CHANGELOG.md` a aktualizuj verzi na konci `README.md`.
- **Rozhodnutí z `to-do/` se přesouvá do `design.md`** a z `to-do/` zmizí.
- Hodnoty (barvy, velikosti, řezy) drž na jednom místě v `design.md`; ostatní soubory
  na něj odkazují, neopisují.
- Písmo se vyvíjí u svého zdroje (odkaz v `README.md`). Soubory písma tady neupravuj
  ani negeneruj — jen je nahrazuj novou verzí ze zdroje a uprav číslo verze v README
  a `design.md`.
- Dokumentace je česky.

## Co nikdy nedělat

- **Repo je na GitHubu veřejné.** Cokoli sem napíšeš, uvidí každý. Žádné interní cesty
  (k disku, k jiným projektům), údaje o počítačích, zálohách, účtech, klíče, hesla,
  osobní údaje ani interní plány. Jen věcná pravidla designového systému.
- **Licence písma (SIL OFL 1.1) se musí dodržet:**
  - u písma vždy zůstává `assets/fonts/OFL.txt` s copyrightem; nemazat ho, nezkracovat,
  - písmo se nesmí prodávat samostatně a upravené verze musí zůstat pod OFL,
  - copyright v metadatech fontů neměnit.
- **Loga a název GeekBoy jsou ochranná známka**, licence písma se na ně nevztahuje.
  Neměň v README pravidla jejich použití bez výslovného zadání.
- Necommitovat archiv starých verzí (`_archiv/` je v `.gitignore`).

Stav projektu: STAV.md (po větší změně aktualizuj).
