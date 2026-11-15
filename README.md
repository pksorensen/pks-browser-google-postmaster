# pks-browser-google-postmaster

Browser-opskrifter til Google Postmaster Tools, kørt **lokalt** af [Agentics browser-tray](https://agentics.dk/products/pks-agent-browser).

**[Åbn opskrifterne på agentics.dk →](https://agentics.dk/browser/recipes/pksorensen/pks-browser-google-postmaster)**

## Opskrifter

| Fil | Hvad den gør | Profil |
| --- | --- | --- |
| [`recipes/google-postmaster-tilfoej.json`](recipes/google-postmaster-tilfoej.json) | Tilføjer et domæne og læser verifikationsposten (TXT) ud | `google` |
| [`recipes/google-postmaster-bekraeft.json`](recipes/google-postmaster-bekraeft.json) | Trykker Verify, når TXT-posten ligger i DNS | `google` |
| [`recipes/google-postmaster-rapport.json`](recipes/google-postmaster-rapport.json) | **Udkast.** Læser de sidste 7 dages tal for alle domæner. Kun læse-verber | `google` |

## Et nyt domæne

1. Kør `google-postmaster-tilfoej` med `domain`. Resultatet har `verifikation[0].value`,
   altså `google-site-verification=…`.
2. Læg den som TXT-post på domænets apex. Det sker uden for trayen, fordi opskrifterne
   ikke kan tale med andre tjenester end den side de står på.
3. Kør `google-postmaster-bekraeft` med samme `domain`.

Du logger selv ind på Google i vinduet. Opskriften rører ikke dit kodeord, og den
fortsætter først når domænelisten er fremme.

Hvorfor ikke Postmaster-API'et? Det kræver en OAuth-klient og nøgler. Det her
kræver kun at du er logget ind.

## Installér

Tryk **Installér i trayen** eller **Kør nu** på [opskriftssiden](https://agentics.dk/browser/recipes/pksorensen/pks-browser-google-postmaster).
Trayen viser en kvittering med commit, værter og aftryk, og spørger hver gang.
