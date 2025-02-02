---
icon: /media/railway.png
label: Railway
tags: guides
---

# Setting up is-a.dev with Railway

## Getting the CNAME Record

1. Navigate to the [dashboard](https://railway.app/dashboard)
2. Navigate to the project.
3. Navigate to the service.
4. Switch to the **Settings** tab.
5. Click on **+ Custom Domain** button.
6. Enter the `is-a.dev` subdomain you want to use.
7. Copy the **Value** field.
8. For the domain, make the json like this:
```json
{
  "owner": {
    "username": "your-username",
    "email": "your-email"
  },
  "record": {
    "CNAME": "is-a-dev-docs.pages.dev"
  }
}
```
9. After you have made the file, you should make a pull request.
!!!
**Adding the website preview is neccessary**, since the CNAME value Railway gives you doesn't actually show you the website you are running.
!!!


**If the PR has been merged, the DNS records will be updated in a few minutes.**
**If the PR has been merged but the DNS records haven't updated and you have waited 48 hours, open a GitHub issue or a help thread in the is-a.dev discord server.**
