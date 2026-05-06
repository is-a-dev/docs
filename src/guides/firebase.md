---
order: 1350
icon: /media/firebase.svg
label: Firebase
tags: guides
---

# Setting up Firebase Hosting with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Firebase Hosting site and pointing your is-a.dev subdomain towards it.

## Creating a Firebase Project

First, create a Firebase project and set up Firebase Hosting. Follow the instructions in the [Firebase Hosting Documentation](https://firebase.google.com/docs/hosting/quickstart).

### Setting up Firebase Hosting

1. Install the Firebase CLI: `npm install -g firebase-tools`
2. Initialize Firebase in your project directory: `firebase init hosting`
3. Deploy your site: `firebase deploy`

### Creating the Domain File

Create a JSON file inside the `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
  "owner": {
    "username": "github-username",
    "email": "me@example.com"
  },
  "records": {
    "CNAME": "your-firebase-site.web.app"
  }
}
```

Make sure to replace:

- `github-username` with your actual GitHub username
- `me@example.com` with your email address
- `your-firebase-site.web.app` with your hosting site

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

### Configuring Firebase Hosting for Custom Domain

After your pull request is merged and your is-a.dev subdomain is active:

1. Go to your Firebase Console
2. Navigate to **Hosting** in the left sidebar
3. Click **Add custom domain**
4. Enter your is-a.dev subdomain (e.g., `example.is-a.dev`)
5. Firebase will verify domain ownership automatically through DNS
6. Wait for the SSL certificate to be provisioned (this can take up to 24 hours)

## Notes

- Firebase Hosting automatically provides SSL certificates for custom domains
- Make sure your Firebase project is deployed and accessible before adding the custom domain

## Troubleshooting

If you encounter issues:

- Ensure your Firebase project is deployed and accessible via the default `.web.app` domain
- Check that your DNS records have propagated (this can take up to 48 hours)
- Verify your Firebase Hosting configuration in `firebase.json`
- Make sure your build files are in the correct public directory specified in your Firebase configuration
