---
order: 1700
label: Codeberg Pages
icon: /media/codeberg.svg
tags: guides
---

# Setting up Codeberg Pages with an is-a.dev subdomain

This guide will walk you through the process of setting up a Codeberg Pages website and pointing your is-a.dev subdomain to it.

## Create a Codeberg Pages Website

First, you'll need to create a website on Codeberg Pages. Follow the instructions in the [Codeberg Pages Guide](https://docs.codeberg.org/codeberg-pages/).

### Create the Domain File

Create a JSON file inside domains directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "your-codeberg-username",
        "email": "your-email@example.com"
    },
    "records": {
        "CNAME": "pages.your-codeberg-username.codeberg.page"
    }
}
```

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

### Add `.domains` file

Once your PR is merged, Make a `.domains` file to point your website to your new `.is-a.dev` domain and add your subdomain (`your-subdomain.is-a.dev`) to it.

### Done!

If you've followed everything correctly your website should be live :)
