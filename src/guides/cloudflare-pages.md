---
order: 1900
label: Cloudflare Pages
icon: /media/cloudflare.svg
tags: guides
---

# Setting up Cloudflare Pages with an is-a.dev subdomain

This guide will walk you through the process of setting up a Cloudflare Pages website and pointing your is-a.dev subdomain towards it.

## Create a Cloudflare Pages Website

First, you'll need to create a website on Cloudflare Pages. Follow the instructions in the [Cloudflare Pages Getting Started Guide](https://developers.cloudflare.com/pages/get-started/guide/).

### Point your subdomain to your Cloudflare Pages site

Next, you'll need to point your is-a.dev subdomain to your Cloudflare Pages website. Follow the instructions in the [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Only follow the "Add a custom domain" section, and then return to this guide for the next steps.

### Create the Domain File

In the `domains` directory, create a new JSON file for your subdomain (`domains/subdomain.json`) and submit a pull request. This file should contain the following:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email@example.com"
    },
    "records": {
        "CNAME": "your-sitename.pages.dev"
    }
}
```

### Your website should be live!

If you have followed all the steps correctly, then your website should be live after your pull request has been merged.
