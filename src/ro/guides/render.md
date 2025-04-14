---
icon: /media/render.svg
label: Render
tags: guides
---

# Configurarea Render cu subdomeniul is-a.dev

Acest ghid vă va arăta procesul de configurare a unui deployment Render și conectarea subdomeniului is-a.dev la acesta.

## Crearea unui serviciu Render

Mai întâi, va trebui să creați un serviciu pe Render. Urmați instrucțiunile din [Documentația Render](https://docs.render.com/).

### Crearea fișierului pentru domeniu

Creați un fișier JSON în directorul `domains` (`domains/subdomain.json`) cu următorul conținut și trimiteți un pull request:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "A": ["216.24.57.1"]
    }
}
```
**Notă:** În secțiunea owner, puteți adăuga orice cont de social media, cum ar fi Discord. Dacă adăugați un alt cont de social media, puteți omite câmpul email. Cu toate acestea, numele de utilizator GitHub este obligatoriu. Nu uitați să furnizați o previzualizare a site-ului în pull request-ul dumneavoastră.

## Configurarea Render

- După ce pull request-ul este aprobat, va trebui să configurați serviciul Render pentru a utiliza noul subdomeniu. Accesați panoul de control al serviciului Render.
- Navigați la **Settings > Custom Domains** și adăugați `subdomain.is-a.dev` în câmpul furnizat.
- Render va oferi un pas de verificare, care de obicei necesită adăugarea unei înregistrări DNS. Acest pas poate fi sărit dacă subdomeniul dumneavoastră indică deja către adresa IP Render (`216.24.57.1`).

### Pași Finali

- Așteptați ca modificările DNS să se propage. Acest lucru poate dura de la câteva minute până la câteva ore.
- Serviciul dumneavoastră Render ar trebui să fie acum accesibil la `subdomain.is-a.dev`.
