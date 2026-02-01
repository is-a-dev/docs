---
order: 1800
icon: /media/vercel.svg
label: Vercel
tags: guides
---

# Setting up Vercel with an is-a.dev subdomain

This guide will walk you through the process of setting up a Vercel site and pointing your is-a.dev subdomain towards it.

## Ensure you have a Vercel site

If you haven't made a Vercel site, make sure to make one. Follow the instructions in [Vercel's Docs](https://vercel.com/docs/getting-started-with-vercel).

### Creating the domain

1. Navigate to your Vercel dashboard. Then, navigate to the "Domains" tab of your project's settings. Click "Add Domain" and enter the is-a.dev subdomain you want (e.g. `example.is-a.dev`).
!!!
You may see Vercel enable by default the "Redirect example.is-a.dev to www.example.is-a.dev" button. We recommend to disable it since it will make the main subdomain (`example.is-a.dev`) be a redirect to a nested subdomain (`www.example.is-a.dev`) which you would have to make a file for alongside the main subdomain. If you wish to make a file for `www.example.is-a.dev`, copy the same file format as the main subdomain, but replace the records with what Vercel gave you.
!!!
2. Once you're past the "Configure Environment and Redirects" tab—if unsure, just click "Save"—then click "Continue manually". Copy the TXT verification value that you'll get; you'll need this in step 4.
3. [Fork](https://github.com/is-a-dev/register/fork) our repository and create a file **in the `/domains` folder** named `your-domain.json`. Replace `your-domain` with the name of the subdomain you chose earlier in the Vercel dashboard.
4. In this file, paste the following JSON and ***make sure to replace all the values properly***.

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email-address@example.com"
    },
    "records": {
        "A": ["216.198.79.1"]
    }
}
```
!!!
These records could be different so please pay attention and check what records Vercel assigned you with.
!!!

5. Create a second file named `_vercel.your-domain.json` (replace `your-domain` with your chosen subdomain) and add the following content (make sure to replace the TXT record value with your verification string):

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "your-email-address@example.com"
    },
    "records": {
        "TXT": "insert-TXT-string-you-got-from-vercel-here"
    }
}
```
!!!
If you wish to add multiple nested subdomains with Vercel, please add all of the TXT records in this file. For more information on how you can add multiple TXT records please check the [Domain Structure](/useful/domain-structure) section.
!!!

### Make a pull request

Once you have made these two files, you can now make a pull request to the [repository](https://github.com/is-a-dev/register). Then you'll need to be patient until it gets merged. If you want a chance to get your PR merged faster, join our [Discord server](https://discord.gg/is-a-dev-830872854677422150) and send your pull request link ***once*** in `#pull-requests`.

Once the pull request has been merged your site should be working; if it is still redirecting to the is-a.dev site, try clearing your cache.
