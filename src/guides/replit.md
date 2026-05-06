---
order: 1000
icon: /media/replit.svg
label: Replit
tags: guides
---

# Setting up Replit with an is-a.dev subdomain

## Creating a project

Follow the instructions in the [Replit Workspace Guide](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) on how to create a project.

### Connect your repl to your is-a.dev subdomain

Follow the instructions in the [Replit Custom Domains Guide](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl).

Only follow the "Connecting your domain to your repl" section, then return to this guide for the next steps.

### Creating the domain file

Create a JSON file inside `domains` directory (`domains/subdomain.json`) with the following content:

**Note:** Do not add any TXT records, even if Replit instructs you to do so.

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "me@example.com"
    },
    "records": {
        "CNAME": "siteid.id.repl.co"
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

## Finish

Once your pull request has been merged you should be able to visit your new is-a.dev subdomain connected to your Replit site!
