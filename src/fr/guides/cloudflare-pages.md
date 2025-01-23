---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags: guides
---
# Configurer Cloudflare Pages avec un sous-domaine is-a.dev

Ce guide vous guidera pour créer un site Cloudflare Pages et y relier votre sous-domaine is-a.dev.

## Créer un site Cloudflare Pages

Premièrement, vous devez créer un site sur Cloudflare Pages. Suivez les instructions du [Guide de démarrage de Cloudflare Pages (en)](https://developers.cloudflare.com/pages/get-started/guide/).

### Rediriger votre sous-domaine vers votre site Cloudflare Pages

Ensuite, vous devez rediriger votre sous-domaine is-a.dev vers votre site Cloudflare pages. Suivez les instructions du [Guide des domaines personnalisés de Cloudflare Pages (en)](https://developers.cloudflare.com/pages/configuration/custom-domains/#add-a-custom-subdomain). Suivez uniquement la section *"Add a custom subdomain"*, puis revenez à ce guide pour les étapes suivantes.

### Créer le fichier du domaine

Dans le dossier `domains`, créez un nouveau fichier JSON pour votre sous-domaine (`domains/sous-domaine.json`) et soumettez un pull request. Ce fichier doit contenir le JSON suivant :

```json
{
    "owner": {
        "username": "nom-d'utilisateur-github",
        "email": "votre-email@example.fr"
    },
    "record": {
        "CNAME": "votre-site.pages.dev"
    }
}
```

### Votre site est en ligne !

Si vous arrivez jusqu'ici, votre site devrait être en ligne après que votre pull request ait été fusionné.
