---
order: 1200
icon: /media/railway.png
label: Railway
tags: guides
---

# Setting up is-a.dev with Railway

## Getting the CNAME Record

1. Navigate to the [dashboard](https://railway.app/dashboard)
2. Navigate to the project.
3. Navigate to the service.
4. Switch to the **Settings** tab.
5. Click on **+ Custom Domain** button.
6. Enter the `is-a.dev` subdomain you want to use.
7. Copy the **Value** field.
8. For the domain, make the json like this:
```json
{
  "owner": {
    "username": "your-github-username",
    "email": "your-email@example.com"
  },
  "records": {
    "CNAME": "the-value-railway-gave-you"
  }
}
```
9. After you have made the file, you should make a pull request.

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

!!!
**Adding the website preview is mandatory**, since the CNAME value Railway gives you doesn't actually show you the website you are running.
!!!


- **If the PR has been merged, the DNS records will be updated in a few minutes.**
- **If the PR has been merged but the DNS records haven't updated and you have waited 48 hours, [open a GitHub issue](https://github.com/is-a-dev/register/issues/new/choose) or a help thread in the is-a.dev [Discord server](https://discord.gg/is-a-dev-830872854677422150).**
