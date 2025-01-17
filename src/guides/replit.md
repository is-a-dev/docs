---
icon: /media/replit.svg
label: Replit
tags: guides
---

# Setting up Replit with your is-a.dev subdomain

## Creating a project

Follow the instructions in the [Replit Workspace Guide](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) on how to create a project.

### Connect your repl to your is-a.dev subdomain

Follow the instructions in the [Replit Custom Domains Guide](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl).

Only follow the "Connecting your domain to your repl" section, then return to this guide for the next steps.

### Creating the domain file

Create a JSON file inside `domains` directory (`domains/subdomain.json`) with the following content:

**Note:** Do not add any TXT records, even if Replit instructs you to do so.

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "CNAME": "siteid.id.repl.co"
    }
}
```

## Finish

Once your pull request has been merged you should be able to visit your new is-a.dev subdomain connected to your Replit site!
