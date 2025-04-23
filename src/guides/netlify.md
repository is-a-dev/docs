---
icon: /media/netlify.svg
label: Netlify
tags: guides
---

# Setting up Netlify with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Netlify deployment and pointing your is-a.dev subdomain towards it.

## Creating a Netlify Website

First, create a website on Netlify. Follow the instructions in the [Netlify Docs](https://docs.netlify.com/).

### Creating the Domain File

Create a JSON file inside the `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/github-username/github-repository",
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "A": ["75.2.60.5"]
    }
}
```

**Note:** In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your website in your pull request.

## Configuring Netlify
- After your pull request is merged, you may need to configure your Netlify website to use the new subdomain. Visit your Netlify website's dashboard.
- Navigate to **Site Settings > Domain Management > Custom Domains** and add `subdomain.is-a.dev` in the given field.
- Netlify will provide a verification step, usually requiring you to add a DNS record. You should be able to skip this step if your subdomain is already pointing to Netlify's IP address (`75.2.60.5`).

### Final Steps
- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Netlify website should now be accessible at `your-subdomain.is-a.dev`.
