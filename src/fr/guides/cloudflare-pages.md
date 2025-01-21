---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags: guides
---
# Configurer Cloudflare Pages avec un sous-domaine is-a.dev

Ce guide vous guidera à travers le processus de configuration d'un site Cloudflare Pages et de redirection de votre sous-domaine is-a.dev vers celui-ci.

## Créer un site Cloudflare Pages

Premièrement, vous devrez créer un site sur Cloudflare Pages. Suivez les instructions du [Guide de démarrage de Cloudflare Pages (en)](https://developers.cloudflare.com/pages/get-started/guide/).

### Rediriger votre sous-domaine vers votre site Cloudflare Pages

Ensuite, vous devrez rediriger votre sous-domaine is-a.dev vers votre site Cloudflare pages. Suivez les instructions du [Guide des domaines personnalisés de Cloudflare Pages (en)](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Suivez uniquement la section "Ajouter un domaine personnalisé", puis revenez à ce guide pour les étapes suivantes.
Next, you'll need to point your is-a.dev subdomain to your Cloudflare Pages site. Follow the instructions in the [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Only follow the "Add a custom domain" section, then return to this guide for the next steps.

### Create the Domain File

In the `domains` directory, create a new JSON file for your subdomain (`domains/subdomain.json`) and submit a pull request. This file should contain the following:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email@gmail.com"
    },
    "record": {
        "CNAME": "your-sitename.pages.dev"
    }
}
```

### Your site should be live!

If you have followed all the steps correctly, then your site should be live after your pull request has been merged.
