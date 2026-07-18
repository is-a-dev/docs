---
order: 1700
label: Codeberg Pages
icon: /media/codeberg.svg
tags: guides
---

# Setting up Codeberg Pages with an is-a.dev subdomain

This guide will walk you through the process of setting up a Codeberg Pages (or any git-pages host) website and pointing your is-a.dev subdomain to it.

## Create a Codeberg Pages Website

First, you'll need to create a website on Codeberg Pages. Follow the instructions in the [Codeberg Pages Guide](https://docs.codeberg.org/codeberg-pages/).

For detailed and alternative methods, see instructions on [git-pages.org](https://git-pages.org/) or [grebedoc.dev](https://grebedoc.dev/).

## Create the Domain File

Create a JSON file inside domains directory (`domains/subdomain.json`) with the following content:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email@example.com"
    },
    "records": {
        "CNAME": "codeberg.page"
    }
}
```

## Verifying Your Domain

Create a JSON file inside domains directory (`domains/_git-pages-repository.subdomain.json`) with the following content:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email@example.com"
    },
    "records": {
        "TXT": "https://codeberg.org/USERNAME/REPOSITORY.git"
    }
}
```

## Submit a Pull Request

Make sure you have created the above two files properly, and then submit a Pull Request.

## Add a Repository Webhook

- Navigate to the webhooks section of your Codeberg repository: <https://codeberg.org/USERNAME/REPOSITORY/settings/hooks>
- Click `Add webhook` and select `Forgejo` in the dropdown menu.
- Set `Target URL` to `https://subdomain.is-a.dev` and set `Branch filter` to `pages`
- Now submit the form using `Add webhook` button at the bottom.

Now, make sure your site's html and other content is stored in the `pages` branch of your repository.
After your pull request is merged, you can do a push to the pages branch to activate your domain.

### Done!

If you've followed everything correctly your website should be live :)
