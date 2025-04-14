---
icon: /media/netlify.svg
label: Netlify
tags: guides
---

# Configurarea Netlify cu subdomeniu is-a.dev

Acest ghid vă va arăta procesul de configurare a unui deployment Netlify și conectarea subdomeniului is-a.dev la acesta.

## Crearea unui site Netlify

Mai întâi, va trebui să creați un site pe Netlify. Urmați instrucțiunile din [Documentația Netlify](https://docs.netlify.com/).

### Crearea fișierului pentru domeniu

Creați un fișier JSON în directorul `domains` (`domains/subdomain.json`) cu următorul conținut și trimiteți un pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "eu@example.com"
    },
    "record": {
        "A": ["75.2.60.5"]
    }
}
```
**Notă:** În secțiunea owner, puteți adăuga orice cont de social media, cum ar fi Discord. Dacă adăugați un alt cont de social media, puteți omite câmpul de email. Cu toate acestea, numele de utilizator GitHub este obligatoriu. Nu uitați să furnizați o previzualizare a site-ului dvs. în pull request.

## Configurarea Netlify

- După ce pull request-ul este aprobat, ar putea fi necesar să vă configurați site-ul Netlify pentru a utiliza noul subdomeniu. Accesați panoul de control al site-ului dvs. Netlify.
- Navigați la **Site Settings > Domain Management > Custom Domains** și adăugați `subdomain.is-a.dev` în câmpul dat.
- Netlify va oferi un pas de verificare, care de obicei necesită adăugarea unei înregistrări DNS. Acest pas poate fi sărit dacă subdomeniul dvs. este deja îndreptat către adresa IP Netlify (`75.2.60.5`).

### Pași Finali

- Așteptați ca modificările DNS să se propage. Acest lucru poate dura de la câteva minute până la câteva ore.
- Site-ul dvs. Netlify ar trebui să fie acum accesibil la `subdomain.is-a.dev`.
