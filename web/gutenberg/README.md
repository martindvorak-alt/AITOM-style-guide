# Gutenberg komponenty — AITOM web

Dva soubory, jeden zdroj pravdy:

- **`components.json`** ← **tento soubor čti/používej pro tvorbu.** Strojově čitelný registr
  komponent. Pro každou komponentu: `id`, `name`, `category`, `description`, `sourcePages`, `fields`
  (editovatelná místa) a `template` (reálná Gutenberg block markup z živého webu, s `{{placeholder}}`
  na místech, která se mají při generování nahradit). Z tohoto souboru se má reálně generovat
  obsah/stránky.
- **[`../../nahledy/web-components.html`](../../nahledy/web-components.html)** — vizuální přehled
  POUZE pro kontrolu očima (otevři v prohlížeči). Zobrazuje stejná data jako `components.json`, jen
  čitelně — název, popis, editovatelná pole, zdrojová stránka a samotný kód komponenty. Filtrovatelné
  podle kategorie. Nečti ho kvůli tvorbě — je zbytečně velký a pomalý na zpracování, `components.json`
  má úplně stejný obsah v lehčí strojově čitelné formě.

Oba soubory generuje `build_components.py` skript (v scratchpadu, ne v repu) — při přidávání dalších
komponent se dá znovu spustit stejným způsobem, případně stačí ručně upravit `components.json` a
`nahledy/web-components.html` přegenerovat.

## Postup skládání stránky (pro AI nástroj)

Když má AI nástroj z podkladu (brief, hotový HTML/landing page k přestylování, popis stránky) sestavit
Gutenberg stránku, drž se v tomto pořadí:

1. **Nejdřív hledej přesnou shodu** v `components.json` — pokud sekce odpovídá existující komponentě
   (podle `category`/`description`), použij ji a vyplň `{{placeholder}}` pole.
2. **Pokud přesná shoda chybí, najdi nejbližší podobnou** a uprav ji / poskládej sekci z víc existujících
   komponent, než abys psal/psala něco úplně od nuly.
3. **Teprve pokud fakt nic nesedí, navrhni novou komponentu** — ale povinně platí:
   - výstup musí být validní **UAGB/Gutenberg block markup** (ne čisté HTML) — jinak se nedá vložit
     do WP editoru a zůstat tam editovatelná, což je celý smysl tohoto registru,
   - barvy jen z palety v `styleguide.json` (žádné vlastní hex kódy),
   - radius, spacing a další vizuální detaily (rohy, pozadí, odstupy) podle tokenů ve `styleguide.json`
     (`radius_small`/`radius_large`, `spacing.base_unit_px` atd.), ne podle odhadu,
   - dodrž pravidlo "zelená jen jako jeden akcent na stránku" — viz `styleguide.json` → `rules`.
4. **Nově navrženou komponentu vždy pojmenuj a označ jako improvizovanou** ("tohle jsem musel/a
   navrhnout, v registru nebylo") — ať je jasné, co případně stojí za to přidat do `components.json`
   natrvalo, místo aby se to řešilo pokaždé znovu od nuly.

## Jak to funguje (kontext webu)

Web běží na **WordPress + UAGB/Spectra** (page builder plugin) + vlastních **Blockstudio** blocích
(`blockstudio/hero`, `blockstudio/pipes`, `blockstudio/case-study`, `blockstudio/targets`,
`blockstudio/quote`, `blockstudio/testimonials`, `blockstudio/video-player`,
`blockstudio/anchor-menu`, `blockstudio/benefit-table`, `blockstudio/cta`, `blockstudio/solution-graph`).

`blockstudio/pipes` je wrapper konkrétně pro grid servisních "Ikonovy Box 2" karet (celá karta jako
odkaz) — **není** to Double Diamond diagram. Ten používá `blockstudio/solution-graph` (bespoke vizuál,
nízká priorita pro generický registr).

Ikonových boxů je v globálních stylech **6 variant** (Ikonovy Box 1-5, Ikonový box 6) — každá má jinak
umístěnou ikonu a jiné chování CTA (žádné / text link / celá karta jako odkaz). Boxy 5 a 6 bývají navíc
obalené v samostatné bordered kartě (Spojene Boxy / Shrnutí Projektu Radek) — border a radius patří
obalu, ne boxu.

Hodnota `0.001020304` v UAGB atributech je interní "nenastaveno" placeholder, ne skutečná hodnota —
v šablonách v `components.json` je už vyčištěná.

## Synced Patterns (opakovaně použité sekce)

Tyto sekce NEJSOU kopírovaný kód — jsou to centrálně spravované "Synced Patterns" vložené jako
`<!-- wp:block {"ref":ČÍSLO} /-->`. V editoru je vkládej přes **Inserter → Synced patterns** podle
názvu, nekopíruj kód:

| ref | Obsah |
|---|---|
| 361 | Řádek log klientů |
| 823 | Počítadla (projekty/roky/studie/specialisté) + "Vyznáme se v technologiích" |
| 432 | Reference/testimonials klientů |
| 586 | Neznámý obsah — na konci /b2b/ a /tvorba-webu-a-online-aplikaci/ za testimonials, potřeba ověřit v editoru |
| 587 | Neznámý obsah — na konci /b2b/ a /tvorba-webu-a-online-aplikaci/ za testimonials, potřeba ověřit v editoru |

## Aktuální komponenty v registru

hero-primary, section-header, icon-box-checkmark-list (Box 5), stats-counters, numbered-process-steps
(Box 4), checkmark-pill-row, dark-rounded-box, anchor-menu, icon-box-2, icon-box-6, timeline-numbered-steps,
hero-badge, faq-jsonld, services-tabs, vyhody-box, button-default, cta-block, partner-logos-gallery — viz
`../../nahledy/web-components.html` pro detail každé z nich (vizuálně).

## Zdrojové stránky

- Homepage (`/`)
- `/tvorba-webu-a-online-aplikaci/firemni-web/`
- Detail případové studie (Notino)
- `/revenue-operations/`
- `/b2b/`
- `/vstupni-studie/`
- `/tvorba-webu-a-online-aplikaci/`
- `/b2b/` (marketing sekce s FAQ schema, tabs, výhody)

## Co ještě chybí

Komponenty potvrzené vizuálně/strukturálně, ale u kterých ještě chybí přesně zkopírovaný reálný kód pro
JSON (nechceme si markup vymýšlet): **icon-box-1** (Ikonovy Box 1 — ikona nahoře, h4, text CTA link
s šipkou), **case-study-grid** (Cerny Box Pripadovky + uagb/post-masonry). Dál zbývá: tabulka srovnání
(blockstudio/benefit-table), testimonial+video blok, identifikace obsahu Synced Patterns 586/587.

**Tlačítka** — `button-default` (v JSON jen border atributy, ale reálně se renderuje jako PLNĚ
VYPLNĚNÉ tmavé tlačítko s bílým textem — potvrzeno screenshotem `cta-block` od uživatele, oprava
dřívějšího chybného odhadu "jen orámování") a `checkmark-pill-row` (bílá pilulka s fajfkou) jsou
v registru reálně potvrzené. **Zelené vyplněné "primary" tlačítko** (dle vizuálního
`styleguide.json`/design specu) v žádné dosud zkopírované stránce reálně nebylo — pokud ho web na
nějaké stránce používá, doplní se, jakmile přijde reálný kód z editoru.

Doplní se, jakmile bude k dispozici reálně zkopírovaný blok z editoru.
