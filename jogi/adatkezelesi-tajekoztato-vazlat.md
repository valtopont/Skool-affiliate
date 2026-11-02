# Adatkezelési tájékoztató – vázlat és nyitott jogi kérdések (v1.6)

> Nem jogi tanács. Belső munkaanyag, a weboldal-buildből kizárva (`_config.yml`), de a nyilvános repóban olvasható – ezért személyes adatot nem tartalmaz.
> A meglévő, részletes jogi kérdéslistát a projektgazda később adja át; ez a fájl azt nem helyettesíti, csak a v1.6 méréséhez és oldalához kapcsolódó pontokat rögzíti.

## A `privacy.html` tervezet

- Hely: `privacy.html` (a repó gyökerében). Helyőrzők: `[HELYŐRZŐ: …]`, narancs színnel.
- Amíg tervezet: a `_config.yml` kizárja a buildből, az `analytics-config.js` `privacyUrl` mezője üres → a mérés nem indul el, link sincs rá.
- Véglegesítés lépései: helyőrzők kitöltése → jogi ellenőrzés → a „TERVEZET” doboz törlése → `privacy.html` törlése az `exclude` listából → `privacyUrl: 'privacy.html'` → lábléc-link a `HELYŐRZŐ` kommentnél.

## Nyitott jogi kérdések (JOGI KÉRDÉS), a mérés és az oldal szempontjából rangsorolva

1. **Üzemeltetői adatok (Ektv.)** – magánszemélyként mely adatokat kell nyilvánosan közölni, és van-e személyes adatot kímélő megoldás? (Projektgazdai vállalás: név, e-mail; vállalkozási adatok, ha lesz és kell.)
2. **Adatkezelési tájékoztató a GA4-hez** – a `privacy.html` helyőrzői: adatkezelő, címzett (Google), EU-n kívüli adattovábbítás jogalapja, megőrzési idő, sütik élettartama.
3. **Technikai naplók és e-mail** – jogalap és megőrzés (GitHub Pages, levelezőszolgáltató).
4. **Ajánlói közlés** – elég-e a CTA-k melletti közlés és a #reklám jelölés (oldal és Facebook-posztok, később hirdetés)?
5. **Ár közlése** – kell-e bruttó (áfával növelt) ár, vagy elég a „33 USD + áfa/hó” és a hivatkozás a Skool fizetési oldalára?
6. **A céloldal saját kereseti állításai** – milyen felelősség terheli az ajánlót, ha a hivatkozott közösség oldala konkrét kereseti állításokat tesz?
7. **Hirdetés** (csak hivatalos fiókfeloldás után) – reklámközlés, célzás, Meta-hirdetési szabályok; Meta Pixel csak külön döntéssel és hozzájárulással.
8. **Az első jutalék adózása** – az első Skool-jutalék előtt tisztázandó: milyen formában és mikor kell bevallani a külföldi jutalékot (könyvelő/NAV).

## Az oldalról szándékosan kihagyott elemek (helyük `HELYŐRZŐ` kommenttel jelölve)

| Elem | Miért maradt ki | Mi kell a visszakerüléshez |
|---|---|---|
| Élő alkalmak | Nincs nyilvános megerősítés | Projektgazdai döntés + forrás |
| Javasolt lemondási határidő (pl. 24 óra) | Nincs friss súgóellenőrzés | Friss Skool-súgóellenőrzés |
| Visszatérítés | Nincs friss súgóellenőrzés | Friss Skool-súgóellenőrzés |
| Üzemeltetői mondat / impresszum | Jogi döntés nélkül nem közölhető | 1. jogi kérdés lezárása |
| „A közösség vezetőitől is kérdezhetsz” | Nem igazolt, ki válaszol | Forrás + projektgazdai döntés |
| „Magánszemély ajánlói oldala” | Üzemeltetői kérdéshez kötött | 1. jogi kérdés lezárása |
