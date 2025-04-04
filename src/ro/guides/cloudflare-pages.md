---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags: guides
---

# Configurarea Cloudflare Pages cu subdomeniu is-a-dev

Acest ghid vă va arăta procesul de configurare a unui site Cloudflare Pages și conectarea subdomeniului is-a.dev la acesta.

## Creați un Site Cloudflare Pages

Mai întâi, va trebui să creați un site pe Cloudflare Pages. Urmați instrucțiunile din [Ghidul pentru creerea unui site pe Cloudflare Pages](https://developers.cloudflare.com/pages/get-started/guide/).

### Conectați subdomeniul către site-ul Cloudflare Pages

În continuare, va trebui să conectați subdomeniul is-a.dev către site-ul dvs. Cloudflare Pages. Urmați instrucțiunile din [Ghidul Domenilor Personalizate Cloudflare Pages](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Urmați secțiunea "Add a custom domain", apoi reveniți la acest ghid pentru pașii următori.

### Creați Fișierul pentru Domeniu

În directorul `domains`, creați un nou fișier JSON pentru subdomeniul dvs. (`domains/subdomain.json`) și trimiteți un pull request. Acest fișier ar trebui să conțină următoarele:


```json
{
    "owner": {
        "username": "numele-github",
        "email": "email@exemple.com"
    },
    "record": {
        "CNAME": "numele-sitelui.pages.dev"
    }
}
```

### Site-ul dvs. ar trebui să fie live!

Dacă ați urmat toți pașii corect, site-ul dvs. ar trebui să fie live după ce pull request-ul dvs a fost acceptat.

