---
order: 1200
icon: /media/railway.png
label: Railway
tags: guides
---

# Setting up is-a.dev with Railway

## Getting the CNAME Record

1. Navigate to the [dashboard](https://railway.app/dashboard) > project > service
2. Switch to the **Settings** tab and click on **+ Custom Domain** button.
3. Enter the `is-a.dev` subdomain you want to use (ex: `subdomain.is-a.dev`)
4. Copy the **Value** field for `@` and create `subdomain.json`
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
5. Copy the **Value** field for `_railway-verify` and create `_railway-verify.subdomain.json`
  ```json
  {
    "owner": {
      "username": "your-github-username",
      "email": "your-email@example.com"
    },
    "records": {
      "TXT": "the-value-railway-gave-you"
    }
  }
  ```
6. After you have made the two file, you should make a pull request.

!!!
**Adding the website preview is mandatory**, since the CNAME value Railway gives you doesn't actually show you the website you are running.
!!!

- **If the PR has been merged, the DNS records will be updated in a few minutes.**
- **If the PR has been merged but the DNS records haven't updated and you have waited 48 hours, [open a GitHub issue](https://github.com/is-a-dev/register/issues/new/choose) or a help thread in the is-a.dev [Discord server](https://discord.gg/is-a-dev-830872854677422150).**
