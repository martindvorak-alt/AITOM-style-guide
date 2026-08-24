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

## Odvozené údaje

- **Záloha** bývá 50 % z ceny díla — pokud uživatel výši zálohy sám neurčí jinak, dopočti ji jako
  50 % ze smluvní ceny bez DPH.

## Poznámka ke zdrojovému souboru

Sekce "Harmonogram tvorby webu" má ve vzoru neúplnou větu ("Nyní počítáme s") následovanou prázdným
zvýrazněným boxem — tohle je artefakt už v původním (neanonymizovaném) AITOM zdrojovém souboru, ne
chyba anonymizace. Při použití vzoru tuhle část buď doplň reálným harmonogramem, nebo smaž.
