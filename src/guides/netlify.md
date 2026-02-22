---
order: 1600
icon: /media/netlify.svg
label: Netlify
tags: guides
---

# Setting up Netlify with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Netlify deployment and pointing your is-a.dev subdomain towards it.

## Creating a Netlify Website

First, create a website on Netlify. Follow the instructions in the [Netlify Docs](https://docs.netlify.com/).

## Adding the domain to Netlify

To get the records for Netlify, navigate to **Site Settings > Domain Management > Custom Domains** and add `subdomain.is-a.dev` (as an example, you should add the domain which you want to register) in the given field.

### Creating the Domain File

You should see two domains that Netlify added, `subdomain.is-a.dev` and `www.subdomain.is-a.dev`. You have to make both of them so that you can successfully add a domain to Netlify. (`subdomain` being your domain name of choice, of course)

Create a JSON file inside the `domains` directory called `subdomain.json` with the following content:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "A": ["75.2.60.5"]
    }
}
```
!!!
Note: In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your website in your pull request.
!!!

After that, create another JSON file in the same directory called `www.subdomain.json` with the following content:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "CNAME": "website.netlify.app"
    }
}
```
!!!
Note: The CNAME record should be what Netlify gave you, which should be most of the time the website's domain which Netlify generated, like `website.netlify.app`.
!!!

After you've made both of the files, make a pull request and wait.

## Configuring Netlify
- After your pull request is merged, you should be able to connect the domain with Netlify.

### Final Steps
- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Netlify website should now be accessible at `your-subdomain.is-a.dev`.
