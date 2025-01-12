---
label: ImprovMX
icon: /media/improvmx.svg
tags:
    - guides
---

# ImprovMX mit deiner is-a.dev subdomain einrichten



## Voraussetzungen

1. Ein ImprovMX-Konto. Wenn du kein Konto hast, klicke [hier](https://improvmx.com) und erstelle einen.
2. Du solltest bereits die [is-a.dev Repository](https://github.com/is-a-dev/register) geforkt🍴 haben. Erstelle einen über [diesen Link](https://github.com/is-a-dev/register/fork).

## Datei erstellen

Erstelle eine neue Datei im `domains` Ordner namens `deine-subdomain.json`.

Füge das hier in die Datei ein:
```json
{
    "owner": {
        "username": "github-nutzername",
        "email": "meine@normale-email.addresse"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**Erstelle jetzt ein Pull Request in der[is-a.dev Repository](https://github.com/is-a-dev/register).**

## Konfiguration

Nach spätestens 24 Stunden nach Merge sollte die E-Mail-Addresse funktionieren