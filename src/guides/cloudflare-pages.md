---
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags: guides
---

# Setting up Cloudflare Pages with is-a-dev subdomain

This guide will walk you through the process of setting up a Cloudflare Pages site and pointing your is-a.dev subdomain to it.

## Create a Cloudflare Pages Site

First, you'll need to create a site on Cloudflare Pages. Follow the instructions in the [Cloudflare Pages Getting Started Guide](https://developers.cloudflare.com/pages/get-started/guide/).

### Point your subdomain to your Cloudflare Pages site

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
