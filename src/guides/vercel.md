---
icon: /media/vercel.svg
label: Vercel
tags: guides
---

# Setting up Vercel with is-a.dev subdomain

This guide will walk you through the process of setting up a Vercel site and pointing your is-a.dev subdomain to it.

## Make sure you have a Vercel site.

If you haven't made a Vercel site, make sure to make one. Follow the instructions in [Vercel's Docs](https://vercel.com/docs/getting-started-with-vercel).

### Creating the domain files.

First, go to your Vercel dashboard, then go to your project, then go to Custom Domains and put in there the is-a.dev subdomain you want.

**You will need to make two files to ensure this process goes smoothly**. We will go in order for this section.

1. Make a file for Vercel TXT verification.
   When connecting the domain, you will be greeted with a TXT verification string. To make the file for this one the TXT record should be placed in `_vercel.subdomain.json` in the **domains directory** (replace subdomain with the domain you want of course) and the file should be like this (You can leave email field blank as long as you have another social, but **don't remove the field**):

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "",
        "discord": "insert-discord-user-ID-here"
    },
    "record": {
        "TXT": "insert-TXT-string-you-got-from-vercel-here"
    }
}
```

!!!
**_DON'T MAKE A PULL REQUEST YET_**, we still have to make another file. If you were to make a pull request at this point, we would reject your domain since you are trying to make a nested subdomain on a subdomain you don't own yet. Please proceed to the next step.
!!!

2. Make a file for the main domain.
   Now you need to make a file for the main domain, we have two ways to do it: CNAME and A records. We'll have two different files for these and explain what restricions or stuff you need to do.

Make `subdomain.json` in the **domains directory** (replace subdomain with the domain you want of course) and put in the file one of these types:

**CNAME record**: If you are using CNAME record you don't have to give a preview as you are using the site as the CNAME, but you can't use other record (Like MX and TXT records). **This option is ideal for those who only want to use their domain for their site**.

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "",
        "discord": "insert-discord-user-ID-here"
    },
    "record": {
        "CNAME": "domainname.vercel.app"
    }
}
```

**A record**: If you are using an A record, you would need to give a preview either by putting a link in the comment section of the PR, putting it in the description, or by providing a screenshot of your website. **This option is ideal for those who want to use their domain for their site and email**.

```json
{
    "owner": {
        "username": "insert-github-username-here",
        "email": "",
        "discord": "insert-discord-user-ID-here"
    },
    "record": {
        "A": ["76.76.21.21"]
    }
}
```

### Make your pull request.

Once you have made these two files, you can now make a pull request to the [main repo](https://github.com/is-a-dev/register). Then you will have to be patient until it gets merged. If you want a chance to get your PR merged faster then join our [Discord server!](https://discord.gg/is-a-dev-830872854677422150)

When the pull request has been merged your site should be working, if its still redirecting to the is-a.dev site clear your cache.
