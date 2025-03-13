---
icon: /media/vercel.svg
label: Vercel
tags: guides
---

# Configurarea Vercel cu subdomeniul is-a.dev

Acest ghid te va ajuta în procesul de configurare a unui site Vercel și conectarea subdomeniului tău is-a.dev la acesta.

## Asigură-te că ai un site Vercel.

Dacă nu ai creat încă un site Vercel, asigură-te că faci asta. Urmează instrucțiunile din [Documentația Vercel](https://vercel.com/docs/getting-started-with-vercel).

### Crearea fișierelor pentru domeniu.

Mai întâi, accesează panoul de control Vercel, apoi mergi la proiectul tău, apoi la Domenii Personalizate și introdu acolo subdomeniul is-a.dev pe care îl dorești.

**Va trebui să creezi două fișiere pentru ca acest proces să decurgă fără probleme**. Vom merge în ordine pentru această secțiune.

1. Creează un fișier pentru verificarea TXT Vercel.
   Când conectezi domeniul, vei primi un șir de verificare TXT. Pentru a crea fișierul pentru acesta, înregistrarea TXT trebuie plasată în `_vercel.subdomain.json` în **directorul domains** (înlocuiește subdomain cu domeniul pe care îl dorești, bineînțeles) și fișierul ar trebui să arate astfel:
!!!
Poți de asemenea să înlocuiești emailul cu orice formă de handle de social media (Precum Discord, Twitter, Bluesky, Mastodon etc.).
!!!

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "insert-email-here"
    },
    "record": {
        "TXT": "insert-TXT-string-you-got-from-vercel-here"
    }
}
```

!!!
**_NU FACE ÎNCĂ UN PULL REQUEST_**, mai trebuie să creăm încă un fișier. Dacă ai face un pull request în acest moment, ți-am respinge domeniul deoarece încerci să creezi un subdomeniu imbricat pe un subdomeniu pe care nu îl deții încă. Te rugăm să continui cu următorul pas.
!!!

2. Creează un fișier pentru domeniul principal.
   Acum trebuie să creezi un fișier pentru domeniul principal, avem două modalități de a face acest lucru: înregistrări CNAME și A. Vom avea două fișiere diferite pentru acestea și vom explica ce restricții sau cerințe trebuie să îndeplinești.

Creează `subdomain.json` în **directorul domains** (înlocuiește subdomain cu domeniul pe care îl dorești, bineînțeles) și pune în fișier unul dintre aceste tipuri:

**CNAME**: Dacă folosești o înregistrare CNAME nu trebuie să oferi o previzualizare deoarece folosești site-ul ca CNAME, dar nu poți folosi alte înregistrări (Precum înregistrări MX și TXT). **Această opțiune este ideală pentru cei care vor să folosească domeniul doar pentru site-ul lor**.

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "insert-email-here"
    },
    "record": {
        "CNAME": "domainname.vercel.app"
    }
}
```
**Înregistrare A**: Dacă folosești o înregistrare A, va trebui să oferi o previzualizare fie prin adăugarea unui link în secțiunea de comentarii a PR-ului, fie prin adăugarea acestuia în descriere, sau prin furnizarea unei capturi de ecran a site-ului tău. **Această opțiune este ideală pentru cei care vor să folosească domeniul atât pentru site-ul lor cât și pentru email**.

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "insert-email-here"
    },
    "record": {
        "A": ["76.76.21.21"]
    }
}
```

### Creează pull request-ul tău.

După ce ai creat aceste două fișiere, poți acum să faci un pull request către [repository-ul principal](https://github.com/is-a-dev/register). Apoi va trebui să fii răbdător până când acesta va fi acceptat. Dacă vrei o șansă ca PR-ul tău să fie acceptat mai repede, alătură-te [serverului nostru de Discord!](https://discord.gg/is-a-dev-830872854677422150)

Când pull request-ul a fost acceptat, site-ul tău ar trebui să funcționeze. Dacă încă redirecționează către site-ul is-a.dev, [șterge-ți cache-ul din browser](https://support.google.com/accounts/answer/32050?hl=en&co=GENIE.Platform%3DDesktop)
