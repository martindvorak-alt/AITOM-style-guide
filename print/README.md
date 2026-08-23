# Print dokumenty — AITOM

Tato složka je obdoba `web/` pro tiskové/dokumentové výstupy (PDF, Word) — nabídky, objednávky,
případové studie apod. Na rozdíl od `web/gutenberg/` (kde je jeden JSON registr Gutenberg bloků)
zde má každý typ dokumentu svou vlastní podsložku ve `templates/`, protože jednotlivé typy
dokumentů se liší strukturou i formátem víc než webové sekce.

## Struktura

```
print/
  templates/
    nabidka/            — vzor obchodní nabídky
    objednavka/         — vzor objednávky
    pripadova-studie/   — vzor případové studie (print verze)
```

Každá podsložka bude obsahovat:
- zdrojový vzor dokumentu (Word/PDF nebo šablona z Figmy),
- stručný popis, jaká pole/sekce se v dokumentu mění a jaká zůstávají fixní,
- odkaz na `../../styleguide.html` pro barvy/typografii/logo pravidla, která platí napříč všemi
  tiskovými dokumenty.

## Stav

Zatím jen kostra složek — čeká se na první reálný vzor dokumentu, ze kterého se struktura naplní
stejným způsobem jako `web/gutenberg/components.json` (reálný obsah, ne vymyšlený).
