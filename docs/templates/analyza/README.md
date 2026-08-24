# Vzor — Analýza / obecný strukturovaný dokument

**[`vzor-analyza.docx`](vzor-analyza.docx)** — styleguide-style vzor pro **libovolný delší formátovaný a
strukturovaný dokument** (analýza, audit, report, strategický plán, interní dokumentace apod.) — není vázaný
na konkrétní téma jako SEO/PPC. Na rozdíl od [`../objednavka/`](../objednavka/), kde vzor reprodukuje celý
reálný dokument, tenhle vzor je **záměrně zkrácený na 2 strany** — obsahuje černou úvodní stránku a po
jednom ukázkovém vzoru od každého typu prvku (nadpis kapitoly, nadpis podkapitoly, textový odstavec,
dvojice srovnávacích info-boxů, zelený box, tabulka se zvýrazněným řádkem, odrážkový seznam, tabulka
s prioritami). Zbytek reálného dokumentu (další kapitoly, další řádky tabulek) se doplňuje individuálně
podle rozsahu konkrétního zadání — kopíruj vždy ten blok/tabulku/box, který potřebuješ, a znásob podle
potřeby.

Vychází z reálné SEO/PPC analýzy (anonymizováno a zobecněno — reálný klient, čísla i téma nahrazené
hranatými placeholdery), formátování je uložené jako pojmenované Word styly stejným způsobem jako
u [`../objednavka/`](../objednavka/). Strana 3 doplňuje obecné prvky inspirované reálnou případovou studií
(viz [`../pripadova-studie/`](../pripadova-studie/)) — nadpis úrovně 3, citaci, kroky, statistiky, obrázek
s titulkem, číslovaný seznam a neutrální poznámkový box — aby byly k dispozici i v běžných textových
dokumentech, ne jen v prezentačních materiálech.

## Co je anonymizované / zobecněné

- Doména klienta (`schulte-group.cz`) je nahrazená `[klient]` — v titulní straně i v patičce.
- Typ a název dokumentu (bylo `INDIKATIVNÍ ANALÝZA` / `SEO & PPC`) jsou nahrazené `[TYP DOKUMENTU]` /
  `[Název dokumentu]` — vzor totiž neslouží jen pro analýzy, ale pro jakýkoli formátovaný dokument.
- Obor/vertikála klienta je nahrazená `[Obor / vertikála klienta]`.
- Nepovinná poznámka na obálce (bylo `Datové podklady: Google Search Console, ...`) je nahrazená obecným
  `[Nepovinná poznámka na obálce — např. zdroje dat, verze, datum]` — tahle poznámka nemusí být vždy
  relevantní, klidně ji smaž, pokud dokument žádnou takovou poznámku nepotřebuje.
- Dvojice srovnávacích info-boxů (bylo `SEO — Doporučeno: ANO` / `PPC — Doporučeno: ANO`) je obecný
  srovnávací vzor pro dvě možnosti vedle sebe (`[Možnost A]` / `[Možnost B]`, `Doporučeno: [ANO/NE]`) —
  nemusí jít o srovnání kanálů, funguje pro libovolné dvě porovnávané varianty/scénáře.
- Všechna reálná data, čísla, klíčová slova, konkurenti a doporučení jsou nahrazené hranatými placeholdery
  typu `[Položka 1]`, `[Hodnota]`, `[Popis úkolu.]` — při tvorbě nového dokumentu je nahraď reálným obsahem.

## Struktura vzoru

**Strana 1 — Úvodní (černá) stránka:**
Celostránková černá plocha (`0B0D0B`), logo AITOM, kicker (typ dokumentu), dvouřádkový titulek (bílý
název dokumentu + zelený akcentní řádek s klientem/předmětem), přechodový pruh, podtitulek, popis
oboru/kontextu, volitelná poznámka.

**Strana 2 — Obsahová stránka (vzor od každého typu prvku):**
- Nadpis kapitoly (H1) s číslem
- Textový odstavec
- Dvojice srovnávacích info-boxů (tmavý + světlý) — možnost A vs. možnost B
- Zelený box (klíčové zjištění / shrnutí / poznámka)
- Nadpis podkapitoly (H2) s číslem
- Tabulka s tmavou hlavičkou a zvýrazněným řádkem CELKEM
- Odrážkový seznam
- Tabulka se sloupcem Priorita (ukazuje všechny 4 úrovně)

**Strana 3 — Doplňkové prvky (obecné, použitelné v jakémkoli textovém dokumentu):**
- Nadpis úrovně 3 (H3)
- Citace / reference (blok s citací, jménem, pozicí a firmou)
- Číslované kroky s velkým barevným číslem (např. popis procesu)
- Řádek se statistikami/KPI (velké číslo + popisek, libovolný počet vedle sebe)
- Obrázek s titulkem (šedý placeholder rámeček + popisek pod obrázkem)
- Číslovaný seznam (nativní Word číslování, na rozdíl od odrážek)
- Neutrální šedý poznámkový box (pro poznámky, které nejsou "klíčové zjištění" — proto bez zeleného akcentu)
- Poznámka ke grafům — doporučení použít nativní graf Wordu (viz níže)

Hlavička (logo + drobek `[Typ dokumentu] · [Název dokumentu]`) a patička (`[klient] — [Název dokumentu]`
+ číslo strany) se opakují automaticky na každé straně přes Word header/footer.

## Formátovací styly (Word)

Veškeré formátování je uložené jako pojmenované styly — v panelu Styly ve Wordu se zobrazí jako `AITOM - ...`.

| Styl | Použití |
|---|---|
| `AITOM - Kicker obálky` | malý zelený caps popisek nad titulkem obálky (typ dokumentu) |
| `AITOM - Titulek obálky` | bílý řádek titulku obálky (název dokumentu) |
| `AITOM - Titulek obálky akcent` | zelený řádek titulku obálky (klient/předmět) |
| `AITOM - Podtitulek obálky` | světle šedý podtitulek obálky |
| `AITOM - Popisek obálky` | šedý popis oboru/kontextu na obálce |
| `AITOM - Poznámka obálky` | drobná volitelná poznámka na obálce (zdroje, verze, datum apod.) |
| `AITOM - Nadpis kapitoly` | H1 — číslo kapitoly má STEJNOU barvu jako název (černá), spodní šedá linka |
| `AITOM - Nadpis podkapitoly` | H2 — číslo podkapitoly stejnou barvou jako název |
| `AITOM - Box tmavý nadpis` / `AITOM - Box tmavý text` | nadpis a text v tmavém info-boxu (levá možnost dvojice) |
| `AITOM - Box světlý nadpis` | nadpis ve světlém info-boxu (pravá možnost dvojice); text ve světlém boxu je běžný `Normal` |
| `AITOM - Zelený box popisek` | caps label zeleného boxu (KLÍČOVÉ ZJIŠTĚNÍ / SHRNUTÍ / DOPORUČENÍ apod.) |
| `AITOM - Tabulka nadpis buňky` | text v tmavé hlavičce tabulky |
| `AITOM - Tabulka text buňky` | běžný text v buňce tabulky |
| `AITOM - Tabulka zvýrazněný text` | tučný text ve zvýrazněném řádku (CELKEM) — kombinuj s ručním podbarvením buňky `ECFAD9` |
| `AITOM - Odrážka značka` (znakový) | zelená značka `▪` na začátku odrážky |
| `AITOM - Priorita vysoká` / `střední` / `kritická` / `nízká` (znakové) | barevné popisky priority v tabulkách úkolů |
| `AITOM - Hlavička dokumentu` / `AITOM - Patička dokumentu` | text v running header/footer |
| `AITOM - Tabulka analýzy` (styl tabulky) | jemné šedé ohraničení `E4E6E4` pro datové tabulky |
| `AITOM - Nadpis úrovně 3` | H3 — menší podnadpis uvnitř podkapitoly (Space Grotesk bold, bez čísla nutně) |
| `AITOM - Citace text` | text citace/reference (kurzíva, větší velikost) |
| `AITOM - Citace autor` / `AITOM - Citace role a firma` | jméno a pozice/firma pod citací |
| `AITOM - Krok číslo` (znakový) | velké zelené číslo před textem číslovaného kroku procesu |
| `AITOM - Statistika číslo` / `AITOM - Statistika popisek` | velké číslo a caps popisek ve statistickém/KPI callout bloku |
| `AITOM - Popisek obrázku` | kurzívou psaný popisek pod vloženým obrázkem |
| `AITOM - Číslovaný seznam` | nativní číslovaný seznam Wordu (zelené číslo, na rozdíl od odrážky `▪`) |
| `AITOM - Šedý box popisek` | caps label neutrálního šedého poznámkového boxu (bez zeleného akcentu) |

### Grafy (koláčový, sloupcový, spojnicový…)

Pro grafy použij **nativní graf Wordu** (Vložení → Graf) — negeneruj je jako obrázek ani je nekresli ručně.
Barevné schéma dokumentu (`word/theme/theme1.xml`) je přemapované na značkové barvy AITOM (zelená, černá,
šedá, elektrická limetka), takže výchozí barvy nově vloženého grafu budou automaticky on-brand bez ručního
přebarvování.

### Barvy použité v systému (mimo `../../../styleguide.json`)

Tyto odstíny se v hlavním `styleguide.json` zatím nevedou jako pojmenované tokeny, ale v tomto vzoru
se používají konzistentně:

| Hex | Použití |
|---|---|
| `ECFAD9` | pozadí zeleného info-boxu i zvýrazněného řádku tabulky (CELKEM/total) |
| `3C7A0A` | text labelu v zeleném info-boxu |
| `2E7D0E` | priorita VYSOKÁ |
| `9A7A00` | priorita STŘEDNÍ |
| `B00020` | priorita KRITICKÁ |
| `F8FAF8` | pozadí světlého info-boxu / téměř bílý text v tmavé hlavičce tabulky |

## Jak doplnit nový dokument

1. Zkopíruj `vzor-analyza.docx`, přejmenuj a nahraď `[TYP DOKUMENTU]`, `[Název dokumentu]`, `[klient]`
   a `[Obor / vertikála klienta]` na obálce i v hlavičce/patičce. Nepovinnou poznámku na obálce buď
   doplň, nebo smaž, pokud není relevantní.
2. Za H1 doplň reálný úvodní odstavec, případně dvojici srovnávacích info-boxů a zelený box s klíčovým
   zjištěním — obojí je nepovinné, použij jen pokud se hodí k obsahu dokumentu.
3. Pro každou další kapitolu okopíruj blok nadpisu H1 (nebo H2 pro podkapitoly) a aplikuj příslušný styl —
   číslo kapitoly piš rovnou další v pořadí, barva se převezme ze stylu automaticky (černá, ne zelená).
4. Pro každou tabulku dat okopíruj vzorovou tabulku (hlavička + řádky + volitelně zvýrazněný CELKEM řádek)
   a znásob řádky podle reálného počtu položek.
5. Pro seznam úkolů s prioritou okopíruj vzorovou tabulku a použij jen ty úrovně priority, které reálně
   potřebuješ (není nutné mít všechny 4 v každé tabulce).

## Povinné údaje — doptat se, pokud chybí

- Typ dokumentu a jeho název (pro kicker, titulek obálky a hlavičku/patičku)
- Klient/předmět dokumentu a obor/kontext
- Alespoň hrubá struktura kapitol, pokud se má lišit od vzoru (úvodní shrnutí → aktuální stav/kontext →
  detailní obsah → doporučení/závěr)
- Zda dokument potřebuje nepovinné prvky ze vzoru (poznámka na obálce, srovnávací info-boxy, zelený box,
  tabulka s prioritami) — nejsou povinné, doptej se, jestli se hodí k danému obsahu
