# Audit webu Ford Mondeo Roadtrips

## 1. Layout titulky — hotovo a nahráno

Finální verze (Live štítek pod rámečkem, Show me pilulka nahoře v rámečku) je nahraná a ověřená přímo na disku (obsahová shoda, ne jen velikost souboru) — stabilní, žádné vracení.

## 2. Opraveno při auditu

**Důležité: opravdová regrese, ne jen kosmetika.** Při kontrole se ukázalo, že dvě dřívější opravy na podzimním webu se samy vrátily zpět na starou verzi, i když byly dřív "ověřené":
- Datumy u day-by-day programu (Sep 17/18/19/20) byly zpátky místo obecného "Day 1–4" u všech 5 destinací — opraveno znovu.
- Formát trasy u Soči (byl rozdělený na 4 řádky místo jednoho jako u ostatních destinací) — opraveno znovu.

Tentokrát jsem to ověřila dvakrát po sobě porovnáním celého obsahu souboru (ne jen velikostí/hashem), takže by to teď mělo držet — ale vzhledem k tomu, jak vytrvalý ten problém je, bych doporučila po dalších editacích v GitHub Desktopu vždy zkontrolovat diff před pushnutím, jestli tam skutečně je to, co má být.

Další drobnosti, opravené rovnou:
- Anglický překlep na podzimním webu: "annyoing" → "annoying".
- Anglický překlep na podzimním webu: "Hover over a pin to display **las** route details" → "**the** route details".
- Český překlep na jarním webu: "rozkvětajícího" → "rozkvétajícího" (hero kicker).

## 3. Duplicitní obrázky — žádné nenalezeny

Zkontrolovala jsem všech 80 fotek napříč weby (25 podzim, 30 zima, 25 jaro) pomocí perceptuálního hashování (porovnává vizuální podobnost, ne jen název souboru). Žádné duplicity ani skoro-duplicity — ani v rámci jedné destinace, ani mezi sezónami. Fotky, které jsi sama vyměnila (hochschwab5, gesause5), jsou teď skutečně odlišné od zbytku.

## 4. Responzivita — v pořádku

Testováno na šířkách 320 / 375 / 414 / 768 / 1024 / 1280 px na všech 4 stránkách. Nikde žádné horizontální přetečení, žádné rozbité rozvržení.

## 5. Funkčnost prvků — v pořádku

Otestováno kliky/hover přes automatizovaný prohlížeč:
- Hub: všechny 3 karty správně odkazují na podstránky, CTA i Live štítek na svém místě, animace mají správnou velikost.
- Zima: hover na horský vrcholek správně zvýrazní horu a zobrazí bublinu, tlačítko scroll-nahoru (vločka) se objeví po scrollu, kotvová navigace funguje.
- Podzim a jaro: tlačítko zpět na hub funguje, kotvová navigace funguje.
- Zkontrolovala jsem i strukturu dat pro mapy (souřadnice u všech destinací sedí) a grafy na podzimním webu (všech 6 canvasů má odpovídající ID) — po obsahové stránce jsou v pořádku.

**Jedno omezení:** mapy (Leaflet), ikony (Font Awesome), Google Fonts a grafy (Chart.js) se načítají z externích CDN, které moje testovací prostředí nemůže dostihnout (firemní síťová politika sandboxu). Nemohla jsem je proto vizuálně ověřit v provozu — ale je to čistě omezení mého testovacího prostředí, ne chyba webu. Na živém GitHub Pages s běžným internetem by se měly načíst normálně, jak už to bylo vidět dřív u podzimního a jarního webu. Doporučuju jen mrknout na živý web na mobilu a zkontrolovat, že se mapy/ikony/grafy fakt zobrazují.

## 6. Gramatika a typografie — v pořádku, s pár postřehy k zamyšlení

Prošla jsem veškerý viditelný text na všech 4 stránkách. Kromě výše opravených překlepů žádné vážné chyby. Pár drobností, které jsem **neměnila** (je to tvůj autorský hravý tón a nechtěla jsem do něj zasahovat bez zeptání), ale stojí za zvážení:

- **Zima, Milešovka** — "...v zimě je nutná pevná obuv s protiskluzem (oj), na kamenech bývá led." — ta vsuvka "(oj)" je uprostřed věty, ne na konci jako tvoje ostatní vtípky ("no a co", "nemyslím si" apod.). Možná záměr, možná to mělo být jinde — mrkni, jestli to sedí tam, kde je.
- **Jaro, patička/signoff** — "Doporučuje 10/10 Ozzyu, **kteří** se těší na hlídání k babičce." — pokud je Ozzy jeden pes, gramaticky by mělo být "**který** se těší" (jednotné číslo). Pokud je to schválně za oba pejsky, budiž, ale stojí za kontrolu.
- **Podzim, Hochschwab** — "Attention! Wild free grazing cows. Watch out for free-grazing cows." — dvě věty říkají prakticky totéž za sebou, možná by to šlo zkrátit na jednu.
- **Podzim, mapová popup bublina** — jeden dynamicky generovaný `<img>` (náhled v popup okně mapy) nemá alt text. Drobnost, spíš pro accessibility než pro reálný dopad.
- **Hub, podtext** — "Můžeš začít explorovat obsah." — "explorovat" je anglicismus, který v běžné češtině moc nežije (spíš "prozkoumávat"/"prohlížet si"). Je to ale přesně to, co jsi zadala, takže nechávám na tobě, jestli to chceš takhle hravě, nebo standardněji.

## 7. Celkové shrnutí

Web je po technické stránce v dobrém stavu — žádné rozbité odkazy, žádné duplicitní fotky, funguje responzivně i interaktivně. Jediná skutečná "chyba" byla ta vrácená regrese na podzimním webu (teď opravená a dvakrát ověřená). Zbytek jsou jen kosmetické postřehy k případnému doladění, ne nic, co by bránilo publikaci.
