# Rozhranie Dvadsatjeden

Aktuálny návrh používa čiernu, bitcoinovú oranžovú a vecné slovenské texty. Svetlý editoriálny návrh 1.1.0 bol používateľom odmietnutý; nie je cieľovým vizuálnym smerom.

## Vizuálny systém

- Čierne pozadie a oddelené tmavé plochy s jemnými hranami.
- Bitcoinová oranžová pre hlavné akcie a aktívnu navigáciu; zelená iba pre úspešné stavy.
- Systémové sans písmo pre obsah, monospace pre dátumy a metadáta. Bez externého fontového CDN.
- Kompaktná typografia, malé polomery rohov, jasný kontrast a čitateľné disabled/error stavy.
- Pôvodný bielo-oranžový wordmark Dvadsatjeden v bočnej navigácii a mobilnej hlavičke. SVG je uložené lokálne v `community-web/src/app/logos/logo-dvadsatjeden.svg`; zdrojom je pôvodné [Logo-Mensie.svg](https://www.dvadsatjeden.org/wp-content/uploads/2023/09/Logo-Mensie.svg).
- Vlastná geometrická značka `21` v ikone aplikácie. Hlavná WordPress stránka ani jej logo sa tým nemenia.
- Favicon prehliadača používa pôvodnú oranžovú `21` z hlavného webu, lokálne uloženú v `community-web/public/favicon.png`. Zdroj: [icon-100x100.png](https://www.dvadsatjeden.org/wp-content/uploads/2023/09/icon-100x100.png). PWA ikony majú samostatné súbory.

## Náhľad pri zdieľaní

`community-web/public/og-community-v1.png` je karta 1200 × 630 px s pôvodným wordmarkom, čiernym pozadím a vecným popisom aplikácie. Editovateľný zdroj je `community-web/design/og-community.svg`; PNG je jeho rasterizácia v prehliadači pri rozmere 1200 × 630 a mierke 1. Obrázok neobsahuje živé počty ani dátumy. Pri zmene návrhu použi nový názov PNG a aktualizuj oba odkazy v `index.html`, aby sa obnovili náhľady uložené sociálnymi sieťami.

Open Graph a Twitter metadáta sú priamo v `index.html`, dostupné aj bez JavaScriptu. Odkazy na obrázok používajú absolútnu produkčnú URL. Návrh obrázka vyžaduje výslovné schválenie používateľom pred nasadením; samotný commit ani úspešné CI toto schválenie nenahrádzajú.

V sekcii Nástroje nasledujú po SATFLUX nástroje Linky a Payky. Ich lokálne SVG logá pochádzajú z [linky.fit/icon.svg](https://linky.fit/icon.svg) a [payky.me/pwa-icon.svg](https://payky.me/pwa-icon.svg).

## Rozloženie a texty

Úvod stručne vysvetľuje účel aplikácie: bitcoin udalosti, lokálne komunity a spoločné projekty na Slovensku a v Česku. Obsahuje najbližšie udalosti a odkazy na hlavné funkcie. Stavový panel zobrazuje iba skutočné údaje aplikácie: počet komunít, budúcich udalostí a stav lokálneho účtu. Čas aktualizácie sa vzťahuje výslovne na zoznam komunít, nie na bitcoin sieť.

Nezobrazujeme vymyslené on-chain ukazovatele, falošné online počty ani všeobecné slogany. Navigácia a nadpisy priamo pomenúvajú obsah: kalendár udalostí, mapa komunít, nápady a projekty, účet a nastavenia.

Desktop používa bočnú navigáciu; mobil zachováva päť hlavných sekcií v spodnej lište. Kalendár má podrobný a dátumový pohľad. Mapa, formuláre, modaly, účet a Nostr používajú rovnaký tmavý systém.

## Zachovanie funkcií

Redizajn nemení API ani identitu existujúcich účtov. Zachováva filtrovanie, RSVP, obnovu zo slov, Nostr NIP-07/NIP-46, mapové vrstvy a polohu, priebežné načítanie komunít, nápady, komentáre, hlasy, archiváciu, články, nástroje aj upozornenia. Výsledok sa overuje buildom, testami a izolovanými prehliadačovými scenármi na mobile aj desktope.

## Vývoj a vydanie

Zmeny idú cez novú vetvu, commit, push a PR. Pred mergom musí prejsť CI a dokončené CodeRabbit review najnovšieho commitu. Preskočené review neznamená schválenie. Nasadenie nasleduje až po merge; postup je v CONTRIBUTING.md a AGENTS.md.

## Súbory

- `community-web/src/app/community-app.css`: vizuálny systém a responzivita.
- `community-web/src/features/layout/AppLayout.tsx`: značka, navigácia a názvy sekcií.
- `community-web/src/features/layout/AtlasHero.tsx`: prehľadový panel so skutočnými údajmi. Názov súboru je interný historický názov.
- `community-web/public/favicon.png`: pôvodná favicon hlavného webu.
- `community-web/scripts/generate-icons.mjs`: generovanie samostatných PNG ikon PWA.
- `community-web/design/og-community.svg` a `community-web/public/og-community-v1.png`: zdroj a výsledný obrázok na zdieľanie.
