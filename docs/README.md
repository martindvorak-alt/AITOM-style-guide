# Docs (dokumenty) — AITOM

Tato složka je obdoba `web/` pro tiskové/dokumentové výstupy (PDF, Word) — nabídky, objednávky,
případové studie apod. Na rozdíl od `web/gutenberg/` (kde je jeden JSON registr Gutenberg bloků)
zde má každý typ dokumentu svou vlastní podsložku ve `templates/`, protože jednotlivé typy
dokumentů se liší strukturou i formátem víc než webové sekce.

## Řetězec style guidů (extends)

Web a dokumenty mají odlišná grafická pravidla (typicky typografie — dokument má plynulý tok textu
s vlastním odsazením nadpisů, web skládá layout po komponentách). Aby se nemusela stejná data
duplikovat na víc místech, style guide soubory na sebe navazují přes `"extends"`:

```
../styleguide.json                              — základ, společný pro web i dokumenty
  → styleguide-docs.json                        — co je JINÉ/NAVÍC pro dokumenty obecně
    → templates/<typ>/styleguide-<typ>.json     — co je JINÉ/NAVÍC pro konkrétní typ dokumentu (zatím žádný neexistuje)
```

**Při tvorbě dokumentu vždy načti celý řetězec** (základ + `styleguide-docs.json` + případně
soubor konkrétního typu, pokud existuje) — pozdější soubor v řetězci přebíjí/rozšiřuje ten předchozí,
neduplikuje ho.

- **[`styleguide-docs.json`](styleguide-docs.json)** — typografická pravidla plynulého toku textu
  (odsazení nadpisů, pravidlo pro číslované nadpisy — LIŠÍ SE od webové komponenty), barevná pravidla
  pro dělítka/odrážky a knihovna obecných "stavebních bloků pro dokumenty a prezentace" (karta, tmavá
  karta, tag, citace, ikonový box var 1-4, checklist pilulky, hero/cover strana, zvýrazněný nadpis).

## Struktura

```
docs/
  styleguide-docs.json   — rozšíření ../styleguide.json specifické pro dokumenty (viz výše)
  templates/
    nabidka/              — vzor obchodní nabídky
    objednavka/           — vzor objednávky
    pripadova-studie/     — vzor případové studie (print/PDF verze)
    analyza/               — vzor analytického/reportového dokumentu (SEO/PPC analýza, audit apod.)
```

Každá podsložka v `templates/` bude obsahovat:
- zdrojový vzor dokumentu (Word/PDF nebo šablona z Figmy),
- stručný popis, jaká pole/sekce se v dokumentu mění a jaká zůstávají fixní,
- případně vlastní `styleguide-<typ>.json`, pokud daný typ dokumentu potřebuje další odlišnost od
  `styleguide-docs.json`.

## Stav

`styleguide-docs.json` je hotový a vychází z reálného obsahu `nahledy/styleguide.html` (sekce
"Komponenty" a "Ukázka plynulého textu").

`templates/objednavka/` má hotový reálný vzor (`vzor-objednavka.docx`) — anonymizovaný ze skutečné
klientské objednávky (částky nahrazené `0 Kč` a podbarvené žlutě, klientské údaje jako hranaté
placeholdery).

`templates/analyza/` má hotový vzor (`vzor-analyza.docx`) pro delší analytické/reportové dokumenty —
anonymizovaný ze skutečné SEO/PPC analýzy, ale na rozdíl od objednávky záměrně zkrácený na 2 strany
(styleguide formát: černá úvodní stránka + po jednom vzoru od každého typu prvku — nadpisy, info-boxy,
tabulky, prioritní štítky). `templates/nabidka/` a `templates/pripadova-studie/` jsou zatím jen kostra
složek — čeká se na první reálný vzor, ze kterého se struktura naplní stejným způsobem.
