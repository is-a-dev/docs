# Setting up Cloudflare pages with your is-a.dev subdomain

## Creating a pages.dev site
Follow [their guide](https://developers.cloudflare.com/pages/get-started/guide/) on how to set it up.

## Point your pages.dev site to your is-a.dev subdomain
Follow [their guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain) on how to do it.
Only follow the "Add a custom domain" section and then follow the rest of the steps here.

## Creating the domain file
Create a JSON file inside `domains` directory (`domains/<subdomain>.json`) with the following content:

```json 
{
    "owner": {
        "username": "<github-username>",
        "email": "email@address",
        "twitter": "<twitter-username>"
    },
    "record": {
        "CNAME": "<sitename>.pages.dev"
    }
} 
```

## Configuring
- After your pull request has been merged with the main repository you should be able to visit your new is-a.dev domain and it should show you your pages.dev site
if it doesn't then you have configured your domain wrong.
