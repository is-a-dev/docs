# Setting up GitHub pages with is-a.dev subdomain

## Creating a GitHub pages repository
You can create a GitHub pages website by creating a repository with the name `<github-username>.github.io`. For more information about GitHub pages, please read through [their guide](https://guides.github.com/features/pages).

## Creating the domain file
Create a JSON file inside `domains` directory (`domains/<subdomain>.json`) with the following content
```json 
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/<github-username>/<github-username>.github.io",
    "owner": {
        "username": "<github-username>",
        "email": "email@address",
        "twitter": "<twitter-username>"
    },
    "record": {
        "CNAME": "<username>.github.io"
    }
} 
```

## Configuring
- After the pull request is merged, you will see a **404** error on `<your-subdomain>.is-a.dev`. To fix this, go to your GitHub pages repository's **Settings > GitHub pages > Custom domain** and add `<your-subdomain>.is-a.dev` in the given field. _Only do this **after** your pull request is merged._
- Check the **Enforce HTTPS** checkbox below the custom domain input.

## Using is-a.dev for all GitHub Pages sites in your account
It is possible to have a unique subdomain on your is-a.dev domain for each repository which has Pages enabled.

In order to utilise this, you must ensure the following conditions are met:
1) The website which hosts the "root" (`<subdomain>.is-a.dev`) *must* be named `<username>.github.io`
2) That repo *must* have `<subdomain>.is-a.dev` as the custom domain within the Pages settings.
3) Every other repo *must not* have a custom domain set in the Pages settings.
4) Links to these hosted repos *must* end with `/` (e.g `https://<subdomain>.is-a.dev/<project>/`)
