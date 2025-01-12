---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags:
    - guides
---

# Cloudflare Pages mit einer is-a.dev Subdomain einrichten
This guide will walk you through the process of setting up a Cloudflare Pages site and pointing your is-a.dev subdomain to it.

## Eine Cloudflare Pages-Seite erstellen

First, you'll need to create a site on Cloudflare Pages. Follow the instructions in the [Cloudflare Pages Getting Started Guide](https://developers.cloudflare.com/pages/get-started/guide/).

### Die Subdomain zu deiner CF-Pages-Seite zeigen lassen
Next, you'll need to point your is-a.dev subdomain to your Cloudflare Pages site. Follow the instructions in the [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Only follow the "Add a custom domain" section, then return to this guide for the next steps.

### Die Domain-Datei erstellen

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

### Glückwunsch, deine Seite ist jetzt live!

If you have followed all the steps correctly, then your site should be live after your pull request has been merged.
