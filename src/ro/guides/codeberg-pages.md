---
label: Pagini Codeberg
icon: /media/codeberg.svg
tags: ghiduri
---

# Configurarea Paginilor Codeberg cu subdomeniu is-a-dev

Acest ghid vă va arăta procesul de configurare a unui site Codeberg Pages și conectarea subdomeniului is-a.dev către acesta.

## Creați un Site Codeberg Pages

Mai întâi, va trebui să creați un site pe Codeberg Pages. Urmați instrucțiunile din [Ghidul Codeberg Pages](https://docs.codeberg.org/codeberg-pages/).

### Creați Fișierul pentru Domeniu

Creați un fișier JSON în directorul domains (domains/subdomain.json) cu următorul conținut și trimiteți un pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "your-email@gmail.com"
    },
    "record": {
        "CNAME": "pages.your-username.codeberg.page"
    }
}
```
### Adăugați fișierul `.domains`

După ce pull request-ul dvs. este acceptat, creați un fișier `.domains` pentru a direcționa site-ul web către noul dvs. domeniu is-a.dev și adăugați subdomeniul dvs. (`subdomeniul-dvs.is-a.dev`) în acesta.

### Gata!

Dacă ați urmat totul corect, site-ul dvs. web ar trebui să fie live :)
