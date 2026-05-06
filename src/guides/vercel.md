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
You may see Vercel enable by default the "Redirect example.is-a.dev to www.example.is-a.dev" button. We recommend to disable it since it will make the main subdomain (`example.is-a.dev`) be a redirect to a nested subdomain (`www.example.is-a.dev`), which you would have to make a file for alongside the main subdomain. If you wish to make a file for `www.example.is-a.dev`, repeat step 4 like you did with the main subdomain, but replace the records with what Vercel gave you.
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
If you wish to add multiple nested subdomains with Vercel, please add all of the TXT verification records to this file. For more information on how you can add multiple TXT records please check the [Domain Structure](/useful/domain-structure) section.
!!!

### Make a pull request

Once you have made these two files, you can now make a pull request to the [repository](https://github.com/is-a-dev/register). Then you'll need to be patient until it gets merged. If you want a chance to get your PR merged faster, join our [Discord server](https://discord.gg/is-a-dev-830872854677422150) and send your pull request link ***once*** in `#pull-requests`.

### Opening a Pull Request (PR)

Once you have made a new file or made changes to an existing file, you can create a pull request. open creating a pull request you will see a default pull request message which should show:

```
<!--
YOU MUST FILL OUT THIS TEMPLATE FOR YOUR PR TO BE ACCEPTED!
-->

# Requirements
<!-- Your domain MUST pass ALL the requirements below, otherwise it WILL BE DENIED. -->
<!-- Change each checkbox to [x] (all lowercase, with no spaces between the brackets) to mark it as completed. -->

- [ ] I **agree** to the [Terms of Service](https://is-a.dev/terms). <!-- Your request MUST follow the TOS to be approved. -->
- [ ] My file is following the [domain structure](https://docs.is-a.dev/domain-structure/). <!-- Your JSON file is in the domains directory, the name is valid, etc. -->
- [ ] My website is **reachable** and **completed**. <!-- We do not permit simple "Hello, world!" or simply copied template websites with minimal changes. -->
- [ ] My website is **software development** related. <!-- Only your root subdomain needs to meet this requirement. -->
- [ ] My website is **not for commercial use**. <!-- Your website's purpose should not be to generate any form of revenue or profit. -->
- [ ] I have provided contact information in the `owner` key. <!-- Provide your email in the `email` field or another platform (e.g. X/Twitter or Discord) for contact. -->
- [ ] I have provided a preview of my website below. <!-- This step is required for your PR to be approved. -->

# Website Preview
<!-- Provide a link AND screenshot of your website below. if not provided your PR will be closed with no questions asked. -->
# Website Purpose
<!-- Please tell us the purpose or motive behind your website. For example, it is a portfolio website, etc. -->

```

Once you seer the pull request message, replace all the "[ ]" with a lowercase "x" such that it looks like "[x]". Also provide the link to your current site with a screenshot of the site preview and provide the purpose of the site.

Once the pull request has been merged your site should be working; if it is still redirecting to the is-a.dev site, try clearing your cache.
