# Váltópont – ajánlói landing (v1.6)

Magyar nyelvű, mobil-first ajánlói (affiliate) bemutatóoldal a Skoolon működő „Szabadúszó, Affiliate Közösség”-hez.

- **Éles cím:** https://valtopontonline.hu/ (GitHub Pages, publikáló ág: `ccr-9d38271e-ox4er1`)
- **Szlogen:** „Előbb készség, aztán pénz.” – kis méretben a láblécben
- **Felépítés:** probléma → „Mi ez?” → megoldás → mit találsz benne → kinek való → ár és feltételek → GYIK → záró CTA

Statikus HTML + CSS + egy kis JavaScript. Nincs build lépés, nincs függőség, nincs backend.

## Fájlstruktúra

```
.
├── index.html            # az oldal teljes tartalma
├── style.css             # stílusok (színek a :root változóiban)
├── script.js             # beúszó elemek, mobilos sticky CTA, lebegő fejléc
├── analytics-config.js   # GA4 mérési azonosító + a végleges tájékoztató címe (privacyUrl)
├── analytics.js          # hozzájárulási sáv, GA4 (Basic Consent Mode), affiliate_click esemény
├── privacy.html          # adatkezelési tájékoztató – TERVEZET, helyőrzőkkel, a buildből kizárva
├── jogi/                 # jogi vázlat és nyitott kérdések – a buildből kizárva
├── favicon.ico
├── assets/               # logó, favicon, Open Graph-kép (og-kep.png, 1200×630), betűk
├── tests/                # automatikus böngészős tesztek – a buildből kizárva
├── videos/               # belső videóterv – a buildből kizárva
└── README.md             # a buildből kizárva
```

A `_config.yml` `exclude` listája a belső fájlokat kizárja a weboldal-buildből. **A kizárás nem teszi őket priváttá:** a nyilvános repóban olvashatók.

## Tartalmi szabályok

- Nincs bevételi ígéret, garancia, kitalált vélemény vagy szám, álsürgetés, visszaszámláló.
- A közösség vezetőjének neve és a hozzá kapcsolható más márkanév sehol nem szerepelhet (szöveg, metaadat, komment).
- **Díj:** 33 USD + áfa/hó, havonta automatikusan megújuló tagság. Próbaidő nincs (a korábbi 7 napos próba 2026. november 1-jén megszűnt, nem írható vissza).
- **Ajánlói közlés a CTA-k közelében:** fejléc („Ajánlói link”), hero ajánlatsor („Skool · 33 USD + áfa/hó · ajánlói link”), „Mi ez?” blokk (teljes közlés), Ár és feltételek (teljes közlés a CTA fölött), záró CTA és mobilos sticky sáv (rövid közlés), lábléc (teljes ajánlói tájékoztatás).
- Az „ellenőrizd a Skoolon” mondat csak egyszer szerepel, az Ár és feltételek résznél.
- Forrásjelölés HTML-kommentben, ahol az állítás tagi megerősítésen vagy képernyőképen alapul. A `HELYŐRZŐ` kommentek a jogi vagy friss ellenőrzésre váró részek helyét jelölik; látható szöveg nem tartozik hozzájuk.

## Az öt CTA

Mind az öt ugyanoda mutat, új lapon (`target="_blank"`, `rel="noopener sponsored"`):

`https://www.skool.com/szabaduszo-affiliate/about?ref=9f8501e9ce73465b9c9ea3abf13c00f2`

| Hely | `data-cta` | `id` |
|---|---|---|
| Fejléc | `fejlec` | – |
| Hero | `hero` | `hero-cta` |
| Ár és feltételek | `dontes` | `kozepso-cta` |
| Záró CTA | `zaro` | `final-cta` |
| Mobilos sticky sáv | `sticky` | – |

A `data-cta` csak a méréshez kell; a link címe, a `target` és a `rel` nem változik tőle.

## Mérés (GA4, hozzájárulással)

- GA4-tulajdon: „Kattintasmero”, mérési azonosító: `G-0G7W9BEY5S` (`analytics-config.js`).
- **Biztonsági zár:** a mérés csak akkor aktív, ha az `analytics-config.js`-ben a `privacyUrl` ki van töltve. Amíg üres, nincs sáv, nincs süti, nincs tárolás és nincs Google-kérés.
- Bekapcsolás sorrendje: a `privacy.html` véglegesítése (jogi ellenőrzéssel) → a `privacy.html` törlése a `_config.yml` `exclude` listájából → `privacyUrl: 'privacy.html'` → a lábléc helyőrzőjénél link a tájékoztatóra.
- Aktív állapotban hozzájárulási sáv jelenik meg („Elfogadom” / „Elutasítom”, egyforma gombok); a döntés a lábléc „Süti-beállítások” gombjával módosítható.
- Basic Consent Mode: döntés előtt és elutasítás után a `gtag.js` nem töltődik be. Az `ad_storage`, `ad_user_data`, `ad_personalization` mindig `denied`.
- Események: egy `page_view` oldalbetöltésenként; `affiliate_click` a Skool-linkekre (`cta_location` = a `data-cta` értéke, `cta_text`, `ad_variant`, `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`). Az `affiliate_click` nem bizonyít regisztrációt vagy jutalékot.
- A GA4-be küldött oldal-URL csak a négy `utm_*` paramétert tartalmazza (`fbclid`, `gclid` és minden más elmarad).
- **A GA4-fiókban kézzel állítandó:**
  - Bővített mérés → „Kimenő kattintások” KI és „Oldalváltások böngészőelőzmény alapján” KI (különben egy Skool-kattintás duplán számolódik);
  - Adatgyűjtés és -módosítás → Adatmegőrzés → Eseményadatok megőrzése: **14 hónap** → Mentés (nem visszamenőleges).
- **Amit a GA4 nem lát:** azokról, akik nem fogadják el vagy figyelmen kívül hagyják a sávot, semmit – se látogatást, se forrást, se CTA-kattintást. A GA4-számok ezért alsó becslések.
- Meta Pixel nincs a kódban.

### UTM (csak a saját landing URL-en, a Skool-linken soha)

```
https://valtopontonline.hu/?utm_source=facebook&utm_medium=oldal|csoport|komment|profil|paid_social&utm_campaign=<kampány>&utm_content=<posztkód vagy hirdetésváltozat>
```

Hirdetésnél `utm_medium=paid_social`, és az `utm_content` első betűje (`A_…`, `B_…`) a GA4-ben `ad_variant`-ként külön látszik.

## Tesztek

Nincs `package.json`; a Node beépített tesztfuttatója és a már telepített Playwright fut:

```
NODE_PATH=$(npm root -g) node --test tests/*.test.js
```

A tesztek a Google-kéréseket helyettesítő szkripttel szimulálják; a valódi GA4-adatgyűjtést a GA4 DebugView-ban kell kézzel ellenőrizni (`?valtopont_test=1`, csak elfogadott hozzájárulás mellett).

## Korábbi anyagok

A korábbi WordPress/Elementor megvalósítási útmutató az első (v1) dizájnhoz és a megszűnt próbaidős ajánlathoz készült, ezért kikerült; a git-előzményekben visszakereshető.
