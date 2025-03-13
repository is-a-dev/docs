---
label: GitHub Pages
icon: mark-github
tags: guides
---

## Configurarea GitHub Pages cu subdomeniu is-a.dev

Acest ghid vă va arăta procesul de configurare a unui site GitHub Pages și conectarea subdomeniului is-a.dev la acesta.

### Crearea unui repository GitHub Pages

Mai întâi, va trebui să creați un site pe GitHub Pages. Urmați instrucțiunile din [Ghidul GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages).

### Crearea fișierului pentru domeniu

Creați un fișier JSON în directorul `domains` (`domains/subdomain.json`) cu următorul conținut și trimiteți un pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "CNAME": "github-username.github.io"
    }
}
```

### Configurare

- După ce pull request-ul este acceptat, este posibil să vedeți o eroare **404** pe `subdomain.is-a.dev` sau un site greșit. Pentru a rezolva acest lucru, mergeți la **Settings > GitHub pages > Custom Domain** în repository-ul GitHub Pages și adăugați `subdomain.is-a.dev` în câmpul respectiv. _Faceți acest lucru **doar după** ce pull request-ul a fost acceptat._
- Bifați căsuța **Enforce HTTPS** de sub câmpul pentru domeniul personalizat.
- Așteptați puțin timp și site-ul dvs. ar trebui să fie activ!

## Verificarea domeniului is-a.dev cu GitHub Pages

### Obținerea stringului de verificare

1. Deschideți GitHub, apăsați pe iconița profilului în dreapta sus și apăsați `Settings` (Setări).

![](../../media/github_pages_verification/step_1.png)

2. Apăsați `Pages` (Pagini).

![](../../media/github_pages_verification/step_2.png)

3. Apăsați `Add a domain` (Adăugați un domeniu).

![](../../media/github_pages_verification/step_3.png)

4. În câmpul care apare, introduceți numele domeniului dvs. is-a.dev (ex: `myname.is-a.dev`) și apăsați `Add domain` (Adăugați domeniu).

![](../../media/github_pages_verification/step_4.png)

5. Copiați hostname-ul și șirul de verificare.

![](../../media/github_pages_verification/step_5.png)

### Crearea fișierului pentru domeniu

Creați un fișier JSON în directorul `domains/` numit `domains/hostname.subdomain.json` folosind hostname-ul pe care l-ați copiat la pasul 5 și subdomeniul (`subdomain.is-a.dev`) cu următorul conținut și trimiteți un pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "TXT": "github-verification-string"
    }
}
```
## Configurare

După ce pull request-ul este acceptat, repetați pașii pentru a obține șirul de verificare și apăsați butonul `Verify` (Verifică).
Dacă apare vreo eroare precum `Unable to verify your domain` (Verificarea domainului a eșuat), așteptați câteva minute (uneori până la 24 de ore) deoarece DNS-ul s-ar putea să nu fie încă actualizat.
