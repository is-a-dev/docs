---
label: DanBot Hosting
tags: guides
icon: /media/dbh.png
---

# Configurarea DanBot Hosting cu subdomeniu is-a.dev

Acest ghid vă va arăta procesul de configurare a unui site DanBot Hosting și conectarea subdomeniului is-a.dev la acesta.

## Obținerea IP-ului Proxy

Executați următoarea comandă în [serverul Discord DanBot Hosting](https://discord.gg/dbh) în canalul #commands.

```
dbh!server proxy
```

Veți primi un răspuns ca acesta:

![](../../media/dbh_proxy/1.jpg)

Dacă aveți un plan gratuit, alegeți orice proxy din SUA (notat ca US) sau puteți folosi Proxy-ul pentru Donatori dacă sunteți Donator, apoi copiați adresa IP a proxy-ului ales.

### Crearea fișierului pentru domeniu

Creați un fișier JSON în directorul `domains` (`domains/subdomain.json`) cu următorul conținut și trimiteți un pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "A": ["proxy-ip-here"]
    }
}
```

**Notă:** În secțiunea owner, puteți adăuga orice cont de social media, cum ar fi Discord. Dacă adăugați un alt cont de social media, puteți omite câmpul email. Cu toate acestea, numele de utilizator GitHub este obligatoriu. Nu uitați să furnizați o previzualizare a site-ului în pull request-ul dvs.

## Configurare

După ce pull request-ul este acceptat, obțineți ID-ul serverului dvs. rulând această comandă:

```
dbh!server list
```

O să obțineți o listă de servere și ID-ul serverului dvs.

![](../../media/dbh_proxy/2.jpg)

Copiați ID-ul serverului dvs. și rulați următoarea comandă:

```
dbh!server proxy your-subdomain.is-a.dev yourserverid
```
