# Adatkezelési tájékoztató – vázlat és nyitott jogi kérdések (v1.6)

> Nem jogi tanács. Belső munkaanyag, a weboldal-buildből kizárva (`_config.yml`), de a nyilvános repóban olvasható – ezért személyes adatot nem tartalmaz.
> A meglévő, részletes jogi kérdéslistát a projektgazda később adja át; ez a fájl azt nem helyettesíti, csak a v1.6 méréséhez és oldalához kapcsolódó pontokat rögzíti.

## A `privacy.html` tervezet

- Hely: `privacy.html` (a repó gyökerében). Helyőrzők: `[HELYŐRZŐ: …]`, narancs színnel.
- Amíg tervezet: a `_config.yml` kizárja a buildből, az `analytics-config.js` `privacyUrl` mezője üres → a mérés nem indul el, link sincs rá.
- Véglegesítés lépései: helyőrzők kitöltése → jogi ellenőrzés → a „TERVEZET” doboz törlése → `privacy.html` törlése az `exclude` listából → `privacyUrl: 'privacy.html'` → „Adatkezelési tájékoztató” link a lábléc Kapcsolat-sorába (a kapcsolati e-mail mellé).

## Nyitott jogi kérdések (JOGI KÉRDÉS), a mérés és az oldal szempontjából rangsorolva

1. **Üzemeltetői adatok (Ektv.)** – magánszemélyként mely adatokat kell nyilvánosan közölni, és van-e személyes adatot kímélő megoldás? (Projektgazdai vállalás: név, e-mail; vállalkozási adatok, ha lesz és kell.)
2. **Adatkezelési tájékoztató a GA4-hez** – a `privacy.html` helyőrzői: adatkezelő, címzett (Google), EU-n kívüli adattovábbítás jogalapja, megőrzési idő, sütik élettartama.
3. **Technikai naplók és e-mail** – jogalap és megőrzés (GitHub Pages, levelezőszolgáltató).
4. **Ajánlói közlés** – elég-e a CTA-k melletti közlés és a #reklám jelölés (oldal és Facebook-posztok, később hirdetés)?
5. **Ár közlése** – kell-e bruttó (áfával növelt) ár, vagy elég a „33 USD + áfa/hó” és a hivatkozás a Skool fizetési oldalára?
6. **A céloldal saját kereseti állításai** – milyen felelősség terheli az ajánlót, ha a hivatkozott közösség oldala konkrét kereseti állításokat tesz?
7. **Hirdetés – FÜGGŐBEN.** A csatornáról a projektgazda még dönt; a hirdetési kérdéslista a döntés után készül. Megkerülés nem lehetséges megoldás. A mérés csatornafüggetlen (UTM + GA4); követőpixel csak külön döntéssel és hozzájárulással kerülhet be.
8. **Az első jutalék adózása** – az első Skool-jutalék előtt tisztázandó: milyen formában és mikor kell bevallani a külföldi jutalékot (könyvelő/NAV).

## Az oldalról szándékosan kihagyott elemek

Az `index.html`-ben nincs helyőrző komment (élesben bárki látná). Ha egy elem visszakerül, ez a lista mondja meg, hová.

| Elem | Miért maradt ki | Mi kell a visszakerüléshez | Hová kerülne |
|---|---|---|---|
| Élő alkalmak | Nincs nyilvános megerősítés | Projektgazdai döntés + forrás | „Mit találsz” – Közösség és mentorcsoport; GYIK „Milyen segítségre számíthatok?” |
| Üzemeltetői mondat / impresszum | Jogi döntés nélkül nem közölhető | 1. jogi kérdés lezárása | Lábléc, a kapcsolati sor fölött |
| Link az adatkezelési tájékoztatóra | A `privacy.html` még tervezet | 2. jogi kérdés lezárása, `privacyUrl` kitöltése | Lábléc, a kapcsolati sorban |
| „A közösség vezetőitől is kérdezhetsz” | Nem igazolt, ki válaszol | Forrás + projektgazdai döntés | GYIK „Milyen segítségre számíthatok?” |
| „Magánszemély ajánlói oldala” | Üzemeltetői kérdéshez kötött | 1. jogi kérdés lezárása | Lábléc / „Mi ez?” |

## Visszakerült elemek

| Elem | Hol | Forrás |
|---|---|---|
| Lemondás menete (webes menü és mobilapp), a tagság a számlázási időszak végéig tart | GYIK „Hogyan mondhatom le?” | Skool-súgó, 99. és 116. cikk, és a menü a projektgazda fiókjában, 2026-11-02 |
| Javasolt lemondás legalább 24 órával a következő terhelés előtt | ugyanott | ugyanaz |
| Nincs automatikus visszatérítés; a feltételeket a közösség adminjai határozzák meg | ugyanott | ugyanaz |
