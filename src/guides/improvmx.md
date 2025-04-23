---
label: ImprovMX
icon: /media/improvmx.svg
tags: guides
---

# Setting up ImprovMX with an is-a.dev subdomain

This guide will walk you through the process of setting up ImprovMX with your is-a.dev subdomain.

## Requirements

1. You must have an ImprovMX account. If you don't have an ImprovMX account, please visit [their website](https://improvmx.com) and create an account.
2. You should have already forked the [is-a.dev repository](https://github.com/is-a-dev/register). If you haven't forked the repository, please make one by using [this link](https://github.com/is-a-dev/register/fork).

## Creating the file

Visit your fork and navigate into the `domains` directory and create a file. The file should be named in this manner: `subdomain.json`. (Replace `subdomain` with the subdomain name that you want.)

After you've made the file, it should look like this:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**After you've made the file, make a pull request to the [is-a.dev repository](https://github.com/is-a-dev/register).**

## Configuring

After your pull request has been merged, the MX records should be recognized automatically and start working. If you haven't configured it beforehand, please go to the [ImprovMX dashboard](https://app.improvmx.com/) and add the subdomain there.
