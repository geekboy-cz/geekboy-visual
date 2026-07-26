# GeekBoy — Motion Design System v2

> Načti navíc [design.md](design.md). Dlouhá verze: `reference/motion-megaprompt.md`.
> Animace jsou „duší" značky — GeekBoy video je **přesná vizualizace dat**, ne hýbající se obrázek.

## Charakter (Brand Physics)
- Přesný, kontrolovaný, rychlý, ale ne agresivní.
- Minimální elasticita — žádné gumové/bouncy efekty. Důraz na čitelnost.
- Kontinuální tok informací, žádné zbytečné prostoje.

## ⛔ Zakázané patterny
- BounceIn / ElasticOut (dětinské).
- BackOut s velkým overshootem (nestabilní).
- Rotace při vstupu dat (data rostou, netočí se).
- Scale + Rotate dohromady.
- Náhodné směry — každý pohyb má logiku.
- Lineární interpolace u viditelných prvků.

## Easing křivky
```json
{
  "fastOut":        [0.16, 1, 0.3, 1],
  "smoothInOut":    [0.65, 0, 0.35, 1],
  "uiReveal":       [0.16, 1, 0.3, 1],
  "dataGrowth":     [0.22, 1, 0.36, 1],
  "layoutMove":     [0.4, 0, 0.2, 1],
  "microOvershoot": [0.34, 1.56, 0.64, 1]
}
```
- `uiReveal` → fade/scale in, řádky tabulek, karty, tooltipy.
- `dataGrowth` → sloupce, hodnoty, line draw.
- `layoutMove` → přesuny UI, resize, reorder.
- `microOvershoot` → jen luxusní mikroanimace, ne u grafů.
- Overshoot max 3–5 % cíle, návrat do 30 % času, tlumení > 70 %.

## Délky a vzdálenosti
```json
{
  "duration_ms": { "micro": 180, "small": 300, "medium": 500, "large": 700 },
  "distance_px": { "micro": 12, "panel": 32, "scene": 80 }
}
```
- Mikro prvek: 8–16 px · Panel/karta: 24–48 px · Celá scéna: 60–120 px.
- ⛔ Nikdy slide > 300 px (přes půl obrazovky).

## Prostorová logika
- Grafy: vstup vertikálně zespodu (Y+) nebo fade-in.
- Data narůstají ve směru osy (nahoru / doprava).
- Sekundární prvky přilétají z menší vzdálenosti než hlavní obsah.

## Opacity rampa
- Opacity neroste lineárně — kopíruje easing pohybu.
- `0 → 1` dosaženo už v 70 % délky pohybu (prvek je plně viditelný, než se zastaví).

## Rytmus & hierarchie (stagger)
- Max 1 komplexní efekt (glow/scale/overshoot) na kompozici.
- Max 2 současně animující primární prvky.
- Pořadí vykreslení: 1. mřížka + osy (statické) → 2. data (křivky/sloupce) → 3. popisky + legendy.
- Stagger 2–6 snímků mezi skupinami.

## Technické konstanty
- `fps_independence: true`, `deterministic: true` — animace odvozuj z `frame`/`fps`, ne z reálného času.
