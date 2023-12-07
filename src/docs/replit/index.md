# Setting up GitHub pages with is-a.dev subdomain

## Creating a project
Follow [their guide](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) on how to set it up.

## Point your Replit to your is-a.dev subdomain
Follow [their guide](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl) on how to do it.

Only follow the "Connecting your domain to your repl" section and then follow the rest of the steps here.

## Creating the domain file
Create a JSON file inside `domains` directory (`domains/<subdomain>.json`) with the following content:

**Please do not add any TXT records even if Replit tells you to do so.**

```json 
{
    "owner": {
        "username": "<github-username>",
        "email": "email@address",
        "twitter": "<twitter-username>"
    },
    "record": {
        "CNAME": "<sitename>.id.repl.co"
    }
} 
```

## Configuring
- After your pull request has been merged with the main repository you should be able to visit your new is-a.dev domain and it should show you your replit site
if it doesn't then you have configured your domain wrong.
