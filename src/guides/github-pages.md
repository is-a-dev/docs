---
label: GitHub Pages
icon: mark-github
tags: guides
---

## Setting up GitHub pages with is-a.dev subdomain

This guide will walk you through the process of setting up a GitHub Pages site and pointing your is-a.dev subdomain to it.

### Creating a GitHub Pages repository

First, you'll need to create a site on GitHub Pages. Follow the instructions in the [GitHub Pages Getting Started Guide](https://docs.github.com/en/pages/getting-started-with-github-pages).

### Creating the domain file

Create a JSON file inside `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/github-username/github-repository",
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "CNAME": "github-username.github.io"
    }
}
```

### Configuring

- After the pull request is merged, you may see a **404** error on `subdomain.is-a.dev` or the wrong site. To fix this, go to your GitHub pages repository's **Settings > GitHub pages > Custom Domain** and add `subdomain.is-a.dev` in the given field. _Only do this **after** your pull request is merged._
- Check the **Enforce HTTPS** checkbox below the custom domain input.
- Wait some time and your site should be live!

## Verifying your is-a.dev Domain with GitHub Pages

### Get your verification string

1. Open GitHub, press on your profile icon on the top right, and press `Settings`.

![](../media/github_pages_verification/step_1.png)

2. Press `Pages`.

![](../media/github_pages_verification/step_2.png)

3. Press `Add a domain`.

![](../media/github_pages_verification/step_3.png)

4. In the field that appears, type your is-a.dev domain name (e.g. `myname.is-a.dev`) and press `Add domain`.

![](../media/github_pages_verification/step_4.png)

5. Copy the hostname and the verification string.

![](../media/github_pages_verification/step_5.png)

### Create the domain file

Create a JSON file inside the `domains/` directory called `domains/hostname.json` using the hostname you copied in step 5 with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "TXT": "github-verification-string"
    }
}
```

### Configuration

After your pull request has been merged, repeat the steps to get the verification string and press the `Verify` button.
If it shows any error such as `Unable to verify your domain`, try waiting a few minutes (sometimes up to 24 hours) as the DNS change might not have reflected on the DNS server.
