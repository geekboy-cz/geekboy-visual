# GeekBoy Visual

Designový systém a značkové podklady GeekBoy na jednom místě — písma, loga, ikony, barvy
a pravidla, jak z toho stavět. Slouží k tvorbě videí, webu, aplikací, grafů i merche.

Hlavní dokument je **[`design.md`](design.md)**. Všechny hodnoty jsou v něm; ostatní soubory
jsou detaily k jednotlivým disciplínám.

---

## Kde začít podle toho, co děláš

| Dělám… | Přečti si |
|---|---|
| **motion design, Remotion, video** | `design.md` — hlavně kapitoly 5–9 · pak `motion.md` |
| **web nebo aplikaci** | `design.md` + příloha A · fonty a barvy níž v Rychlém startu |
| **grafiku, miniatury, sociální sítě** | `design.md` — kapitoly 1–10 |
| **grafy a datovou vizualizaci** | `design.md` kapitola 15 · `charts.md` |
| **merch a tiskoviny** | `design.md` — kapitoly 3, 4 a 6 · tiskové CMYK verze log v `assets/logos/` |
| **sázím ikony** | `icons.md` · soubory v `assets/images/` |

---

## Co je uvnitř

```
design.md              designový systém — začni tady
motion.md              pohyb: easing, délky, stagger, prostorová logika
icons.md               sada 253 ikon a mapování veličina → ikona
charts.md              grafy a datová vizualizace
CHANGELOG.md           historie verzí systému

assets/fonts/          GeekBoy statické řezy, VF a GeekBoy Display (OTF, WOFF, WOFF2, TTF)
assets/logos/          loga ve všech variantách + tiskové CMYK PDF
assets/images/         253 ikon a obrázky
assets/others/         kompletní balíček ikon ke stažení

to-do/                 co ještě není rozhodnuté nebo dodělané
```

---

## Rychlý start

Výchozí sada — statické řezy Regular a Bold plus Display na hlavní nadpis:

```css
@font-face{
  font-family:"GeekBoy";
  src:url("assets/fonts/geekboy-regular.woff2") format("woff2");
  font-weight:400; font-style:normal; font-display:swap;
}
@font-face{
  font-family:"GeekBoy";
  src:url("assets/fonts/geekboy-bold.woff2") format("woff2");
  font-weight:700; font-style:normal; font-display:swap;
}
@font-face{
  font-family:"GeekBoy";
  src:url("assets/fonts/geekboy-italic.woff2") format("woff2");
  font-weight:400; font-style:italic; font-display:swap;
}
@font-face{
  font-family:"GeekBoy";
  src:url("assets/fonts/geekboy-bolditalic.woff2") format("woff2");
  font-weight:700; font-style:italic; font-display:swap;
}
@font-face{
  font-family:"GeekBoy Display";
  src:url("assets/fonts/geekboydisplay-extrabold.woff2") format("woff2");
  font-weight:800; font-style:normal; font-display:swap;
}
```

**Variabilní font** ber až na motion projekty, kde se váha animuje nebo se roztahuje
šířka. Rozsahy je nutné deklarovat — **bez nich nefunguje `font-stretch`**:

```css
@font-face{
  font-family:"GeekBoy";
  src:url("assets/fonts/geekboy-vf.woff2") format("woff2-variations"),
      url("assets/fonts/geekboy-vf.ttf") format("truetype-variations");
  font-weight:200 900;
  font-stretch:80% 120%;
  font-style:normal;
  font-display:swap;
}
```

Základní barvy: **GeekBoy Blue `#1148E6`** · **GeekBoy Black `#0B0B0B`**.
Tmavý režim je výchozí. Kompletní palety a sémantické tokeny jsou v `design.md`, kapitola 6.

---

## Písmo

**GeekBoy** je vlastní písmo značky, odvozené z **Hubot Sans**. Vzniklo v dílně
**Sudetype** a jeho zdroj žije na **<https://github.com/jiri-beran/geekboy>**.

> ⚠️ **Písmo se průběžně vyvíjí.** Autor ho aktualizuje a **tenhle repozitář nemusí mít
> nejnovější verzi.** Než ho nasadíš do dlouhodobého projektu, porovnej verzi se zdrojem.
>
> Verze v tomhle repu: **1.003**

Řezy, osy a OpenType featury popisuje `design.md`, kapitola 5.

---

## Licence

**Písma** — GeekBoy vychází z Hubot Sans, které je pod **SIL Open Font License 1.1**.
Odvozené písmo se tou licencí řídí také: smíš ho používat, vkládat do dokumentů a webů
i upravovat, ale nesmíš ho prodávat samostatně a odvozené verze musí zůstat pod OFL.
Závazné znění je v [`assets/fonts/OFL.txt`](assets/fonts/OFL.txt).

**Dokumentace** v tomhle repu (`design.md`, `motion.md` a další texty) je volně k použití
pro práci na výstupech GeekBoy.

## Ochranná známka

**Licence na písma se nevztahuje na značku.** Název **GeekBoy**, logo a všechny jeho
varianty — včetně Lab a Extra — jsou ochranné známky. To, že jsou soubory v tomhle
repozitáři veřejně dostupné, **není svolení k jejich používání**.

Loga smíš použít, když pro GeekBoy nebo s GeekBoy pracuješ, a to podle pravidel
v `design.md`, kapitola 4. Jakékoli jiné použití — vlastní produkty, merch, propagace
nebo cokoli, co by naznačovalo spojení s GeekBoy — vyžaduje **předchozí písemný souhlas**.

---

## Verze

Systém verzuje `design.md` polem `version` v hlavičce. Podle něj poznáš, jestli je tvoje
kopie aktuální. Historie změn je v [`CHANGELOG.md`](CHANGELOG.md).

Aktuální verze: **2.4** (1. 8. 2026)
