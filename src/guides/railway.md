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
    "username": "your-github-username",
    "email": "your-email@example.com"
  },
  "records": {
    "CNAME": "the-value-railway-gave-you"
  }
}
```
9. After you have made the file, you should make a pull request.
!!!
**Adding the website preview is mandatory**, since the CNAME value Railway gives you doesn't actually show you the website you are running.
!!!


- **If the PR has been merged, the DNS records will be updated in a few minutes.**
- **If the PR has been merged but the DNS records haven't updated and you have waited 48 hours, [open a GitHub issue](https://github.com/is-a-dev/register/issues/new/choose) or a help thread in the is-a.dev [Discord server]((https://discord.gg/is-a-dev-830872854677422150)).**
