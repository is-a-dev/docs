---
icon: /media/discord.svg
label: Discord Domain-Verbindung
tags:
    - guides
---

# Discord mit is-a.dev verbinden


1. Öffne deine Discord-App und klicke auf`Nutzereinstellungen`.
   ![](../media/discord/step_1.png)

2. Öffne "Verknüpfungen"
   ![](../media/discord/step_2.png)

3. Klicke `Mehr anzeigen`, danach den Globus.
   ![](../media/discord/step_3.png)

4. Gebe deinen Domainnamen ein (z.B. `deine-subdomain.is-a.dev`).
   ![](../media/discord/step_4.png)

5. Klicke auf `Kopieren` im Inhaltsfeld.
   ![](../media/discord/step_5.png)

### Die Domain-Datei erstellen

Erstelle eine JSON-Datei im `domains/` Ordner namens `_discord.deine-subdomain.json` mit diesem Inhalt:

```json
{
    "owner": {
        "username": "github-nutzername",
        "email": "deine@email.addresse"
    },
    "record": {
        "TXT": "dein-kopierter-text"
    }
}
```

## Konfiguration


Nachdem dein PR akzeptiert wurde wiederhole die Schritte vorher und drücke `Verifizieren`. Wenn ein Fehler erschein, warte 24 Stunden, damit die DNS-Änderungen greifen.