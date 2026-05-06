---
order: 1500
label: ImprovMX
icon: /media/improvmx.svg
tags: guides
---

# Setting up ImprovMX with an is-a.dev subdomain

This guide will walk you through the process of setting up ImprovMX with your is-a.dev subdomain.

## Requirements

1. You must have an ImprovMX account. If you don't have an ImprovMX account, please visit [their website](https://improvmx.com) and create an account.
2. You should have already forked the [is-a.dev repository](https://github.com/is-a-dev/register). If you haven't forked the repository, please make one by using [this link](https://github.com/is-a-dev/register/fork).

## Creating the file

Visit your fork and navigate into the `domains` directory and create a file. The file should be named in this manner: `subdomain.json`. (Replace `subdomain` with the subdomain name that you want.)

After you've made the file, it should look like this:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**After you've made the file, make a pull request to the [is-a.dev repository](https://github.com/is-a-dev/register).**

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

## Configuring

After your pull request has been merged, the MX records should be recognized automatically and start working. If you haven't configured it beforehand, please go to the [ImprovMX dashboard](https://app.improvmx.com/) and add the subdomain there.
