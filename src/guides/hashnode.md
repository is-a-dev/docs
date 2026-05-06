---
order: 1300
icon: /media/hashnode.svg
label: Hashnode
tags: guides
---

# Hashnode Blog

When you create your Hashnode blog, Hashnode provides a free `hashnode.dev` subdomain for you. However, you can alternatively set up your own `is-a.dev` subdomain.

In this guide, you will learn how to accomplish this.

---

1. Log in to your Hashnode account.

1. Click on your **avatar** at the bottom-left corner of the page on **desktop** or top-right corner on **mobile**.
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614932849541/cBNDGKXMj.png?auto=compress)

1. Click on the **Blog Dashboard** option from the popup modal to access your blog's dashboard.
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937218081/InvxVHXDy.png?auto=compress)

1. Navigate to the **Domain** tab and enter your domain without the **www** or **https://** prefix in the text field provided. Then click on the **Update** button to proceed.
   ![Hashnode's Blog Domain Tab](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937377176/0cwddAywO.png?auto=compress)

1. Go to your fork of the `is-a-dev/register` repository, edit your subdomain's JSON file, make sure you remove any old records, then add this to the `record` key and create a PR:

```json
"CNAME": "hashnode.network"
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

## Configuration

Once done, your Hashnode blog should be setup to use your subdomain. These changes could take from 1 hour to around 48 hours, so please be patient. It'll most likely be ready within a hour.

Once the DNS has propagated, you can start enjoying your Hashnode blog with your sweet `.is-a.dev` subdomain!

## Need More Help?

If you encounter any issues or need further assistance, consider the following resources:

- [Hashnode Domain Mapping Guide](https://support.hashnode.com/docs/mapping-domain/): This support article provides detailed instructions on mapping your domain in Hashnode.
- [Hashnode Support Center](https://support.hashnode.com/): For more general help related to Hashnode, visit their Support Center.

Please note that is-a.dev is not affiliated with Hashnode. If you're experiencing issues with your Hashnode blog, please seek help through Hashnode's support channels. We are unable to assist with Hashnode-specific issues.
