---
label: ImprovMX
icon: /media/improvmx.svg
tags: ghiduri
---
# Configurarea ImprovMX cu subdomeniul is-a.dev
Acest ghid te va îndruma prin procesul de configurare a ImprovMX cu subdomeniul tău is-a.dev.

## Ce trebuie să faci înainte de a continua.

1. Să ai un cont ImprovMX. Dacă nu ai un cont ImprovMX, te rugăm să accesezi [site-ul lor](https://improvmx.com) și să îți creezi un cont.
2. Ar trebui să fi făcut deja fork la [repository-ul is-a-dev](https://github.com/is-a-dev/register). Dacă nu ai făcut fork la repository, te rugăm să faci unul folosind [acest link](https://github.com/is-a-dev/register/fork).

## Crearea fișierului.

Mai întâi, accesează fork-ul pe care l-ai creat, apoi intră în directorul `domains` și creează un fișier. Fișierul ar trebui să fie numit astfel: `subdomeniu.json`. (Înlocuiește `subdomeniu` cu numele subdomeniului pe care îl dorești, desigur.)
După ce ai creat fișierul, ar trebui să pui în fișier următoarele:

```json
{
    "owner": {
        "username": "nume-utilizator-github",
        "email": "eu@exemplu.com"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

După ce ai creat fișierul, ar trebui să faci un pull request către [repository-ul is-a-dev](https://github.com/is-a-dev/register).

## Configurare
După ce a fost unit (merged), ar trebui să fie recunoscut automat și să înceapă să funcționeze. Dacă nu l-ai configurat în prealabil, te rugăm să accesezi [panoul de control ImprovMX](https://app.improvmx.com/) și să adaugi domeniul acolo.
