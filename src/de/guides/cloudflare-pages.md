---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags:
    - guides
---

# Cloudflare Pages mit einer is-a.dev Subdomain einrichten
Diese Anleitung führt dich durch den Prozess, eine CF-Pages-Seite einzurichten und diese mit deiner is-a.dev Subdomain zu verbinden.
## Eine Cloudflare Pages-Seite erstellen


Erstelle ersteinmal eine CF-Pages Seite. Folge diesen Instruktionen: [Cloudflare Pages Anleitung (Auf Englisch)](https://developers.cloudflare.com/pages/get-started/guide/)
### Die Subdomain zu deiner CF-Pages-Seite zeigen lassen
Hier ist eine Deutsche Übersetzung der [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Du benötigst nur "Add a custom domain", wenn du das Original verwendest. Wenn du diese Übersetzung verwendest, musst du nichts weiter beachten.

#### Eigene Domain hinzufügen

Um eine eigene Domain hinzuzufügen:

    Logge dich in dein Cloudflare-Dashboard ein.
    Wähle deinen Account in Account Home > Workers & Pages aus.
    Wähle dein Pages-Projekt aus, wähle dann "Custom domains".
    Klicke "Set up a domain".
    Gebe die gewünschte Subdomain ein und klicke "Continue"
Hier ein Bild:
![Bild](https://developers.cloudflare.com/_astro/domains.zq4iMU_J_1jlTEx.webp)


### Die Domain-Datei erstellen

In dem `domains` Ordner, erstelle eine neue JSON-Datei für deine Subdomain (`domains/subdomain.json`) und erstelle ein Pull-Request. Diese Datei sollte folgendes erhalten:

```json
{
    "owner": {
        "username": "dein-github-nutzername",
        "email": "deine-email@dein-email-provider.com"
    },
    "record": {
        "CNAME": "seitenname.pages.dev"
    }
}
```

### Glückwunsch, deine Seite ist jetzt live!

Deine Seite sollte erreichbar sein, nachdem dein PR akzeptiert wurde. Das kann aber ca. 24 Stunden dauern.
