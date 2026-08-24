# Vzor — Objednávka

**[`vzor-objednavka.docx`](vzor-objednavka.docx)** — reálný vzor objednávky (anonymizovaný z konkrétní
klientské objednávky). Zachovává skutečné formulace, strukturu a formátování (barvy/fonty dle
`../../../styleguide.json`, brand fonty vč. embedded Space Grotesk/Inter) — z tohoto souboru vycházej
při tvorbě nové objednávky, neupravuj strukturu ani styl, jen doplň skutečný obsah.

## Co je ve vzoru anonymizované

- Všechny konkrétní **částky jsou nahrazené `0 Kč` a podbarvené žlutě** — při tvorbě nové objednávky
  nahraď žlutá pole skutečnou dohodnutou cenou (a smaž žluté podbarvení).
- Klientské údaje (název firmy, adresa, IČ, DIČ, datum podpisu) jsou nahrazené hranatými placeholdery
  typu `[Název klienta]`, `[Ulice a číslo]`, `IČ: [xxxxxxxx]` — doplň skutečné údaje objednatele.
- V tabulce kalkulace jsou u položek se skutečně specifickým klientským obsahem (např. konkrétní
  počet a jména podstránek, počet jazykových mutací) čísla/výčty nahrazené `[X]`/`[Y]` placeholdery —
  ostatní odrážky (obecný popis rozsahu práce) jsou ponechané beze změny, jsou reálně reálně použitelné
  napříč projekty.
- Zhotovitel (AITOM Digital s.r.o., adresa, IČ, DIČ) NENÍ anonymizovaný — to jsou reálné a stálé údaje
  firmy, zůstávají ve všech objednávkách stejné.

## Povinné údaje — doptat se, pokud chybí

Když má AI nástroj sestavit objednávku a uživatel v zadání nedodá tyto údaje (ani podklady, ze
kterých by šly vyčíst), **musí se doptat**, ne si je vymýšlet nebo nechat prázdné:

**Ke zhotoviteli:**
- Název firmy
- Sídlo (ulice, čp, PSČ, město)
- IČ
- DIČ

**Další části objednávky:**
- Smluvní cena bez DPH
- Termín realizace či rozpětí doby dodání
- Datum podpisu objednávky
- **Harmonogram** — rozpis prací podle typu (např. Design, Frontend, Copywriting, ...) a odhadovaná
  doba trvání každého typu práce (viz sekce [Harmonogram tvorby webu](#harmonogram-tvorby-webu) níže)
- **Položky kalkulace** — konkrétní rozpis položek do tabulky Kalkulace tvorby webu (název položky,
  její dílčí odrážky/rozsah práce, cena za položku)

## Odvozené údaje

- **Záloha** bývá 50 % z ceny díla — pokud uživatel výši zálohy sám neurčí jinak, dopočti ji jako
  50 % ze smluvní ceny bez DPH.

## Práce s podklady od uživatele

Pokud uživatel k zadání přiloží podklady (např. e-mail od klienta, poznámky ze schůzky, existující
nabídku, brief, screenshoty), **je nutné z nich do objednávky přenést reálné texty, odkazy i obrázky**
— ne je jen parafrázovat vlastními slovy nebo vynechat:
- **Texty** — konkrétní formulace popisu rozsahu prací, názvy položek apod. přebírej z podkladu,
  ne generickou parafrázi.
- **Odkazy** — pokud podklad obsahuje URL (např. na Struktura webu, Wireframe, reference), vlož je
  do dokumentu jako skutečné hypertextové odkazy (styl `AITOM - Odkaz (medium)`), ne jako text.
- **Obrázky** — pokud podklad obsahuje obrázky (např. logo klienta, screenshoty, vizuály), vlož je
  do dokumentu na odpovídající místo, nenahrazuj je popisem.

## Harmonogram tvorby webu

Sekce obsahuje tabulku s ukázkovými řádky (Práce 1–5, orientační doba trvání jako "1 týden" /
"1–2 týdny" apod.) — při tvorbě reálné objednávky nahraď obsah tabulky skutečnými fázemi projektu
a jejich odhadovanou dobou trvání (řádky lze přidat/ubrat, styly zůstanou zachované).

## Formátovací styly (Word)

Veškeré formátování ve vzoru je uložené jako pojmenované styly (ne přímé/manuální formátování) —
v panelu Styly ve Wordu se zobrazí jako `AITOM...`. Díky tomu při úpravě textu (např. přidání dalšího
odstavce nebo řádku v tabulce) stačí na nový text aplikovat odpovídající styl a formátování bude
konzistentní se zbytkem dokumentu automaticky.

Hlavní styly ve vzoru:

| Styl (název v panelu Styly) | Použití |
|---|---|
| `AITOM - Nadpis sekce` | hlavní nadpisy sekcí (Předmět objednávky, Smluvní cena, Termín realizace, ...) — se šedou spodní linkou |
| `AITOM - Nadpis přílohy` | nadpis přílohy (Kalkulace tvorby webu) |
| `AITOM - Nadpis podsekce` | menší podnadpisy uvnitř sekce (Kalkulace navrhovaného řešení) |
| `AITOM - Label světlé pozadí` / `AITOM - Label tmavé pozadí` | popisky ZHOTOVITEL/OBJEDNATEL a hlavičky tabulek |
| `AITOM - Adresní řádek` | řádky adresy v ZHOTOVITEL/OBJEDNATEL boxu |
| `AITOM - Odrážka (seznam v tabulce)` | odrážkový seznam (subpoložky u položek kalkulace, poznámky) |
| `AITOM - Důraz SemiBold` (znakový) | tučné zvýraznění v textu (Inter SemiBold) |
| `AITOM - Částka zvýrazněná` (znakový) | částky se žlutým podbarvením (0 Kč placeholdery) |
| `AITOM - Odkaz (medium)` (znakový) | odkazy v textu (Inter Medium) |
| `AITOM - Tabulka harmonogram` / `AITOM - Harmonogram práce` / `AITOM - Harmonogram doba` | tabulka harmonogramu prací |

## Poznámka ke zdrojovému souboru

Text v sekci "Harmonogram tvorby webu" byl doplněn o úvodní větu před tabulkou ("Nyní orientačně
počítáme s tímto rozvržením prací...") — původní vzor obsahoval neúplnou větu bez tabulky, což byl
artefakt v původním (neanonymizovaném) AITOM zdrojovém souboru.
