---
icon: /media/replit.svg
label: Replit
tags: guides
---

# Setting up Replit with your is-a.dev subdomain

## Creating a project
Follow the instructions in the [Replit Workspace Guide](https://docs.replit.com/replit-workspace/introduction-to-workspace#how-to-create-a-repl) on how to create a project.

### Connect your project to your is-a.dev subdomain

Since Replit Workspaces has changed alot, follow the instructions in the [Replit Deployment Custom Domains Guide](https://docs.replit.com/cloud-services/deployments/custom-domains#connecting-your-domain-to-your-deployment). You may need the Replit Deployment subscription to do so, or see [Pricing - Replit](https://replit.com/pricing)

### Creating the domain file

After clicking "Link a Domain" button on your Replit Deployment menu and already typed the domain, you will see this

![image](https://docimg.replit.com/images/deployments/custom-domains/03.png)

(The example screenshot uses their own domain, `hat-tip.cc`. But in our case, it should be `<your subdomain>.is-a.dev`)

Note the IP of the A record, and the TXT value, and

Create a JSON file inside `domains` directory and name it like `<your subdomain>.json` with the following content, then do the pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "A": ["<IP here, listed on the A Record>"],
        "TXT": "<TXT value here, listed on the TXT Record>"
    }
}
```

<!-- as EducatedSuddenBucket's suggestion -->
Make sure to provide the preview on the pull request (not on your JSON files)

Note: In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email and Twitter fields. However, the GitHub username is mandatory. Don't forget to provide a preview of your site in your pull request.

## Finish

Once your pull request has been merged you should be able to visit your new is-a.dev subdomain connected to your Replit site!