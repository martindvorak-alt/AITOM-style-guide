# AITOM — Style guide & šablony

Tento repozitář je zdroj pravdy pro vizuální styl a strukturu výstupů značky AITOM. Je určený pro
libovolný AI nástroj (Claude, ChatGPT, Gemini, ...) — stačí přečíst tento soubor a řídit se odkazy
podle toho, co má vzniknout.

## ⚠️ Pro tvorbu používej JEN "light" soubory, ne `nahledy/`

`nahledy/` obsahuje velké HTML soubory (`styleguide.html`, `web-components.html`) — jsou to jen
**vizuální náhledy pro člověka** (otevři v prohlížeči a koukni se). Pro AI nástroj, který má něco
vytvořit, jsou zbytečně velké a pomalé na zpracování. K samotné tvorbě používej vždy odpovídající
**lehký JSON/strukturovaný soubor**:

| Chci vytvořit / přestylovat | Lehký soubor pro tvorbu | Náhled (jen ke kontrole očima) |
|---|---|---|
| **Cokoliv** — barvy, typografie, logo, ikony (obecná brand pravidla) | [`styleguide.json`](styleguide.json) | [`nahledy/styleguide.html`](nahledy/styleguide.html) |
| **Webovou stránku** (import do WordPress/Gutenberg na aitom.cz) | [`web/gutenberg/components.json`](web/gutenberg/components.json) | [`nahledy/web-components.html`](nahledy/web-components.html) |
| **Tiskový/PDF/Word dokument** (nabídka, objednávka, případová studie...) | [`docs/templates/<typ>/`](docs/) | — |

## Postup pro AI nástroj

1. Nejdřív načti `styleguide.json` — barvy, typografii, spacing pravidla, logo/ikony cesty. Platí
   napříč vším, co se tvoří.
2. Podle cílového formátu (web vs. tiskový dokument) načti buď `web/gutenberg/components.json`,
   nebo příslušnou podsložku v `docs/templates/<typ>/` a postupuj podle jejich README.
3. `web/gutenberg/components.json` obsahuje reálné, ze živého webu zkopírované Gutenberg bloky
   s `{{placeholder}}` místy — pro webovou stránku z nich přednostně skládej výstup. Pokud pro danou
   sekci komponenta chybí (např. přestylováváš hotový cizí HTML landing page do našich komponent),
   smíš navrhnout novou — ale jen podle přesného postupu a pravidel v
   [`web/gutenberg/README.md`](web/gutenberg/README.md) (sekce "Postup skládání stránky"): musí to
   pořád být validní Gutenberg markup, jen barvy/rádius/spacing z `styleguide.json`, a musí to být
   jasně označené jako improvizace, ne tichý výmysl.
4. `docs/templates/<typ>/` bude obsahovat reálné vzory dokumentů (zatím se doplňují) — drž se
   stejného principu: vycházej z reálného vzoru, ne z domněnky, jak dokument vypadá.
5. Soubory v `nahledy/` NEČTI kvůli obsahu pro tvorbu — otvírej je jen když se přímo chceš/má se
   podívat, jak něco vypadá vizuálně.

## Struktura repa

```
styleguide.json        — LIGHT: brand pravidla (barvy, typografie, logo, ikony) — čti tohle
Assets/                — loga, ikony, fonty (reálné zdrojové soubory)
web/
  gutenberg/
    components.json     — LIGHT: registr Gutenberg/UAGB komponent pro web — čti tohle
    README.md
docs/
  templates/
    nabidka/             — vzor obchodní nabídky
    objednavka/          — vzor objednávky
    pripadova-studie/    — vzor případové studie (print/PDF)
nahledy/                — POUZE vizuální náhled pro člověka, nečíst kvůli tvorbě
  styleguide.html
  web-components.html
```
