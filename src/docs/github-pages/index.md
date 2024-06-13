# Setting up GitHub pages with is-a.dev subdomain

This guide will walk you through the process of setting up a GitHub Pages site and pointing your is-a.dev subdomain to it.


## Creating a GitHub Pages repository
First, you'll need to create a site on GitHub Pages. Follow the instructions in the [GitHub Pages Getting Started Guide](https://docs.github.com/en/pages/getting-started-with-github-pages).

## Creating the domain file
Create a JSON file inside `domains` directory (`domains/<subdomain>.json`) with the following content and submit a pull request:
```json 
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/<github-username>/<github-repository>",
    "owner": {
        "username": "<github-username>",
        "email": "<email@address>",
        "twitter": "<twitter-username>"
    },
    "record": {
        "CNAME": "<github-username>.github.io"
    }
} 
```

## Configuring
- After the pull request is merged, you may see a **404** error on `<subdomain>.is-a.dev` or the wrong site. To fix this, go to your GitHub pages repository's **Settings > GitHub pages > Custom Domain** and add `<subdomain>.is-a.dev` in the given field. _Only do this **after** your pull request is merged._
- Check the **Enforce HTTPS** checkbox below the custom domain input.
- Wait some time and your site should be live!
