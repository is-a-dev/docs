---
label: DanBot Hosting
tags: guides
icon: /media/dbh.png
---

# Einrichten von DanBot Hosting mit einer is-a.dev Subdomain

Diese Anleitung führt dich durch den Prozess der Einrichtung einer DanBot-Hosting-Seite und der Verknüpfung Ihrer is-a.dev-Subdomain damit.

## Die Proxy-IP erhalten

Gebe den folgenden Befehl im [DanBot Hosting Discord server](https://discord.gg/dbh) im #commands Kanal ein.

```
dbh!server proxy
```

Du wirst so eine Antwort erhalten:

![Bild](../media/dbh_proxy/1.jpg)

Wenn du den kostenlosen Tarif verwendest, wähle einen US-Proxy, wenn du ein Spender bist, nutze einen Donator-Proxy. Notiere dir dann die IP.

### Die Domain-Datei erstellen

Erstelle eine JSON-Datei im `domains` Verzeichnis (`domains/subdomain.json`) mit dem folgenden Inhalt und erstelle ein Pull-Request:

```json
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/github-username/github-repository",
    "owner": {
        "username": "github-nutzername",
        "email": "ich@beispiel.com"
    },
    "record": {
        "A": ["proxy-ip-hier-einsetzen"]
    }
}
```

* Im "owner" Abschnitt, kannst du auch andere Social-Media Verknüpfungen (z.B. Discord) verwenden, und die E-Mail weglassen. Aber der GitHub-Nutzername ist Pflicht. Vergesse nicht, eine Vorschau deiner Seite im PR hinzuzufügen.

## Konfigurieren

Wenn dein PR gemergt wurde, bekomme deine Server-ID über diesen Befehl im DanBot-Discord:
```
dbh!server list
```

Du bekommst eine Antwort so wie diese:

![Bild](../media/dbh_proxy/2.jpg)

Notiere die Server-ID, sende dann den folgenden Befehl.

```
dbh!server proxy deine-subdomain.is-a.dev deineserverid
```
