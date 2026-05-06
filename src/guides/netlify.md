---
order: 1600
icon: /media/netlify.svg
label: Netlify
tags: guides
---

# Setting up Netlify with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Netlify deployment and pointing your is-a.dev subdomain towards it.

## Creating a Netlify Website

First, create a website on Netlify. Follow the instructions in the [Netlify Docs](https://docs.netlify.com/).

## Adding the domain to Netlify

To get the records for Netlify, navigate to **Site Settings > Domain Management > Custom Domains** and add `subdomain.is-a.dev` (as an example, you should add the domain which you want to register) in the given field.

### Creating the Domain File

You should see two domains that Netlify added, `subdomain.is-a.dev` and `www.subdomain.is-a.dev`. You have to make both of them so that you can successfully add a domain to Netlify. (`subdomain` being your domain name of choice, of course)

Create a JSON file inside the `domains` directory called `subdomain.json` with the following content:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "A": ["75.2.60.5"]
    }
}
```
!!!
Note: In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your website in your pull request.
!!!

After that, create another JSON file in the same directory called `www.subdomain.json` with the following content:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "CNAME": "website.netlify.app"
    }
}
```
!!!
Note: The CNAME record should be what Netlify gave you, which should be most of the time the website's domain which Netlify generated, like `website.netlify.app`.
!!!

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

After you've made both of the files and made a Pull Request the Just wait until a maintainer reviews and merges your Pull Request.

## Configuring Netlify
- After your pull request is merged, you should be able to connect the domain with Netlify.

### Final Steps
- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Netlify website should now be accessible at `your-subdomain.is-a.dev`.
