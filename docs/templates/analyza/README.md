# Vzor — Analýza

**[`vzor-analyza.docx`](vzor-analyza.docx)** — styleguide-style vzor pro delší analytické/reportové dokumenty
(např. SEO/PPC analýza, audit, strategický plán). Na rozdíl od [`../objednavka/`](../objednavka/), kde vzor
reprodukuje celý reálný dokument, tenhle vzor je **záměrně zkrácený na 2 strany** — obsahuje černou úvodní
stránku a po jednom ukázkovém vzoru od každého typu prvku (nadpis kapitoly, nadpis podkapitoly, textový
odstavec, dvojice info-boxů, zelený box, tabulka se zvýrazněným řádkem, odrážkový seznam, tabulka s prioritami).
Zbytek reálného dokumentu (další kapitoly, další řádky tabulek) se doplňuje individuálně podle rozsahu
konkrétního zadání — kopíruj vždy ten blok/tabulku/box, který potřebuješ, a znásob podle potřeby.

Vychází z reálné analýzy (anonymizováno — reálný klient i čísla nahrazené hranatými placeholdery), formátování
je uložené jako pojmenované Word styly stejným způsobem jako u [`../objednavka/`](../objednavka/).

## Co je anonymizované

- Doména klienta (`schulte-group.cz`) je nahrazená `[klient].cz` — v titulní straně i v patičce.
- Obor/vertikála klienta je nahrazená `[Obor / vertikála klienta]`.
- Všechna reálná data, čísla, klíčová slova, konkurenti a doporučení jsou nahrazené hranatými placeholdery
  typu `[Položka 1]`, `[Hodnota]`, `[Popis úkolu.]` — při tvorbě nové analýzy je nahraď reálným obsahem.

## Struktura vzoru

**Strana 1 — Úvodní (černá) stránka:**
Celostránková černá plocha (`0B0D0B`), logo AITOM, kicker (typ dokumentu), dvouřádkový titulek (bílý +
zelený akcentní řádek s doménou klienta), přechodový pruh, podtitulek, popis oboru, poznámka o datových
podkladech.

**Strana 2 — Obsahová stránka (vzor od každého typu prvku):**
- Nadpis kapitoly (H1) s číslem
- Textový odstavec
- Dvojice info-boxů (tmavý + světlý)
- Zelený box (klíčové zjištění)
- Nadpis podkapitoly (H2) s číslem
- Tabulka s tmavou hlavičkou a zvýrazněným řádkem CELKEM
- Odrážkový seznam
- Tabulka se sloupcem Priorita (ukazuje všechny 4 úrovně)

Hlavička (logo + drobek `Indikativní analýza · [Téma]`) a patička (`[klient].cz — [téma] analýza` + číslo
strany) se opakují automaticky na každé straně přes Word header/footer.

## Formátovací styly (Word)

Veškeré formátování je uložené jako pojmenované styly — v panelu Styly ve Wordu se zobrazí jako `AITOM - ...`.

| Styl | Použití |
|---|---|
| `AITOM - Kicker obálky` | malý zelený caps popisek nad titulkem obálky |
| `AITOM - Titulek obálky` | bílý řádek titulku obálky (téma dokumentu) |
| `AITOM - Titulek obálky akcent` | zelený řádek titulku obálky (doména/klient) |
| `AITOM - Podtitulek obálky` | světle šedý podtitulek obálky |
| `AITOM - Popisek obálky` | šedý popis oboru/vertikály na obálce |
| `AITOM - Zdroje obálky` | drobná poznámka o datových podkladech na obálce |
| `AITOM - Nadpis kapitoly` | H1 — číslo kapitoly má STEJNOU barvu jako název (černá), spodní šedá linka |
| `AITOM - Nadpis podkapitoly` | H2 — číslo podkapitoly stejnou barvou jako název |
| `AITOM - Box tmavý nadpis` / `AITOM - Box tmavý text` | nadpis a text v tmavém info-boxu (levý box dvojice) |
| `AITOM - Box světlý nadpis` | nadpis ve světlém info-boxu (pravý box dvojice); text ve světlém boxu je běžný `Normal` |
| `AITOM - Zelený box popisek` | caps label zeleného boxu (KLÍČOVÉ ZJIŠTĚNÍ / SHRNUTÍ / DOPORUČENÍ apod.) |
| `AITOM - Tabulka nadpis buňky` | text v tmavé hlavičce tabulky |
| `AITOM - Tabulka text buňky` | běžný text v buňce tabulky |
| `AITOM - Tabulka zvýrazněný text` | tučný text ve zvýrazněném řádku (CELKEM) — kombinuj s ručním podbarvením buňky `ECFAD9` |
| `AITOM - Odrážka značka` (znakový) | zelená značka `▪` na začátku odrážky |
| `AITOM - Priorita vysoká` / `střední` / `kritická` / `nízká` (znakové) | barevné popisky priority v tabulkách úkolů |
| `AITOM - Hlavička dokumentu` / `AITOM - Patička dokumentu` | text v running header/footer |
| `AITOM - Tabulka analýzy` (styl tabulky) | jemné šedé ohraničení `E4E6E4` pro datové tabulky |

### Barvy použité v systému (mimo `../../../styleguide.json`)

Tyto odstíny se v hlavním `styleguide.json` zatím nevedou jako pojmenované tokeny, ale v analytických
dokumentech se používají konzistentně:

| Hex | Použití |
|---|---|
| `ECFAD9` | pozadí zeleného info-boxu i zvýrazněného řádku tabulky (CELKEM/total) |
| `3C7A0A` | text labelu v zeleném info-boxu |
| `2E7D0E` | priorita VYSOKÁ |
| `9A7A00` | priorita STŘEDNÍ |
| `B00020` | priorita KRITICKÁ |
| `F8FAF8` | pozadí světlého info-boxu / téměř bílý text v tmavé hlavičce tabulky |

## Jak doplnit novou analýzu

1. Zkopíruj `vzor-analyza.docx`, přejmenuj a nahraď `[klient].cz` a `[Obor / vertikála klienta]` na obálce
   i v patičce.
2. Za H1 "Executive summary" doplň reálné shrnutí, dvojici info-boxů a zelený box s klíčovým zjištěním.
3. Pro každou další kapitolu okopíruj blok nadpisu H1 (nebo H2 pro podkapitoly) a aplikuj příslušný styl —
   číslo kapitoly piš rovnou další v pořadí, barva se převezme ze stylu automaticky (černá, ne zelená).
4. Pro každou tabulku dat okopíruj vzorovou tabulku (hlavička + řádky + volitelně zvýrazněný CELKEM řádek)
   a znásob řádky podle reálného počtu položek.
5. Pro seznam úkolů s prioritou okopíruj vzorovou tabulku a použij jen ty úrovně priority, které reálně
   potřebuješ (není nutné mít všechny 4 v každé tabulce).

## Povinné údaje — doptat se, pokud chybí

- Doména/název klienta a obor podnikání (pro obálku a patičku)
- Téma/typ analýzy (SEO & PPC, technický audit, konkurenční analýza apod.)
- Datové podklady/zdroje, ze kterých analýza vychází
- Alespoň hrubá struktura kapitol, pokud se má lišit od vzoru (Executive summary → aktuální stav →
  detailní analýza → doporučení)
