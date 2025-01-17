---
icon: /media/netlify.svg
label: Netlify
tags: guides
---

# Setting up Netlify with is-a.dev Subdomain

This guide will walk you through the process of setting up a Netlify deployment and pointing your is-a.dev subdomain to it.

## Creating a Netlify Site

First, you'll need to create a site on Netlify. Follow the instructions in the [Netlify Docs](https://docs.netlify.com/).

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
    "record": {
        "A": ["75.2.60.5"]
    }
}
```

**Note:** In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your site in your pull request.

## Configuring Netlify

- After the pull request is merged, you may need to configure your Netlify site to use the new subdomain. Go to your Netlify site's dashboard.
- Navigate to **Site Settings > Domain Management > Custom Domains** and add `subdomain.is-a.dev` in the given field.
- Netlify will provide a verification step, usually requiring you to add a DNS record. This step should be skipped if your subdomain is already pointing to Netlify's IP address (`75.2.60.5`).

### Final Steps

- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Netlify site should now be accessible at `subdomain.is-a.dev`.
