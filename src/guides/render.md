---
order: 1100
icon: /media/render.svg
label: Render
tags: guides
---

# Setting up Render with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Render deployment and pointing your is-a.dev subdomain towards it.

## Creating a Render Service

First, create a service on Render. Follow the instructions in the [Render Documentation](https://docs.render.com/).

### Creating the Domain File

Create a JSON file inside the `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "me@example.com"
    },
    "records": {
        "A": ["216.24.57.1"]
    }
}
```

**Note:** In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your website in your pull request.

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

## Configuring Render

- After your pull request is merged, you may need to configure your Render service to use the new subdomain. Go to your Render service's dashboard.
- Navigate to **Settings > Custom Domains** and add `subdomain.is-a.dev` in the given field.
- Render will provide a verification step, usually requiring you to add a DNS record. This step should be skipped if your subdomain is already pointing to Render's IP address (`216.24.57.1`).

### Final Steps

- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Render service should now be accessible at `subdomain.is-a.dev`.
