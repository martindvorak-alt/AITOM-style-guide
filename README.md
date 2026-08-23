# AITOM — Style guide & šablony

Tento repozitář je zdroj pravdy pro vizuální styl a strukturu výstupů značky AITOM. Je určený pro
libovolný AI nástroj (Claude, ChatGPT, Gemini, ...) — stačí přečíst tento soubor a řídit se odkazy
podle toho, co má vzniknout.

## Co číst podle cíle

| Chci vytvořit / přestylovat | Kde najdu podklady |
|---|---|
| **Cokoliv** — barvy, typografie, logo, ikony (obecná brand pravidla) | [`styleguide.html`](styleguide.html) |
| **Webovou stránku** (import do WordPress/Gutenberg na aitom.cz) | [`web/gutenberg/`](web/gutenberg/) — viz `README.md` tam |
| **Tiskový/PDF/Word dokument** (nabídka, objednávka, případová studie...) | [`docs/`](docs/) — viz `README.md` tam a příslušná podsložka v `docs/templates/` |

## Postup pro AI nástroj

1. Nejdřív si přečti `styleguide.html` — barvy, typografii, logo pravidla, která platí napříč vším.
2. Podle cílového formátu (web vs. tiskový dokument) otevři buď `web/gutenberg/README.md`, nebo
   `docs/README.md` a postupuj podle instrukcí tam.
3. `web/gutenberg/components.json` obsahuje reálné, ze živého webu zkopírované Gutenberg bloky
   s `{{placeholder}}` místy — pro webovou stránku z nich skládej výstup, nevymýšlej si vlastní
   Gutenberg markup.
4. `docs/templates/<typ>/` bude obsahovat reálné vzory dokumentů (zatím se doplňují) — drž se
   stejného principu, vycházej z reálného vzoru, ne z domněnky, jak dokument vypadá.

## Struktura repa

```
styleguide.html       — obecný brand style guide (barvy, typografie, logo, ikony)
Assets/               — loga, ikony, fonty
web/
  gutenberg/           — registr Gutenberg/UAGB komponent pro web (components.json + components.html)
docs/
  templates/
    nabidka/            — vzor obchodní nabídky
    objednavka/         — vzor objednávky
    pripadova-studie/   — vzor případové studie (print/PDF)
```
