---
order: 200
icon: /media/bluesky.svg
label: Bluesky Custom Handle
tags: guides
---

# Setting up a Bluesky custom handle with an is-a.dev subdomain

## Get your verification string

1. Open your Bluesky app and go to your profile **Settings**.

   ![](../media/bsky/step_1.png)

2. Open the **Accounts** page.

   ![](../media/bsky/step_2.png)

3. Go to the **:icon-mention: Handle** settings.

   ![](../media/bsky/step_3.png)

4. Click on the "I have my own domain" button.

   ![](../media/bsky/step_4.png)

5. **Enter** your is-a.dev subdomain name in the text input and then **Copy** the TXT string. (e.g. `your-subdomain.is-a.dev`).

   ![](../media/bsky/step_5.png)


### Create your domain file

Create a JSON file inside the `domains/` directory called `domains/_atproto.your-subdomain.json` with the following content and open a pull request:

```json
{
    "owner": {
        "username": "your-github-username"
    },
    "records": {
        "TXT": "bsky-verification-string"
    }
}
```

> [!NOTE]
> Don't forget the comma right above the `"records"` key!

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

After your pull request has been merged, repeat steps 1-5 and press the `Verify DNS Record` button.
If it shows any error such as `Failed to verify handle. Please try again.`, try waiting a few minutes (sometimes up to 24 hours) as the DNS records may not have propagated yet.
