# Ford Mondeo Roadtrips — hub

Jeden repozitář, jedna GitHub Pages adresa, tři weby.

```
/index.html            homepage s 3 tlačítky (hub)
/autumn-2026/           aktuální web (Autumn Nature Expedition) — LIVE
/roadtrip-2/            placeholder "Winter Roadtrip — Coming soon"
/roadtrip-3/            placeholder "Next Roadtrip — Coming soon"
```

## Jak to funguje
Homepage (`/index.html`) má 3 karty/tlačítka, každé odkazuje relativní cestou
na svou podsložku (`autumn-2026/`, `roadtrip-2/`, `roadtrip-3/`). Žádné
externí domény, žádné redirecty — všechno běží pod jednou GitHub Pages URL
(např. `https://tvuj-github-ucet.github.io/nazev-repa/`).

## Přidání dalšího webu / nahrazení placeholderu
1. Připrav si hotový web jako složku se svým `index.html` (+ případně `images/`).
2. Nahraď jí složku `roadtrip-2/` nebo `roadtrip-3/` (klidně i přejmenuj složku,
   jen pak uprav odkaz v `index.html` na hlavní stránce).
3. Uprav kartu na homepage: obrázek, nadpis, popisek, tag ("Live" místo
   "In progress") a `href`.

## Nasazení
Stačí tento obsah nahrát do GitHub repozitáře (root) a v nastavení repa
zapnout GitHub Pages (Settings → Pages → Deploy from branch → `main` / root).
Žádná vlastní doména není potřeba, poběží to na `github.io` adrese.
