---
label: ImprovMX
icon: /media/improvmx.svg
tags: guides
---

# Setting up ImprovMX with is-a.dev subdomain

This guide will walk you through the process of setting up ImprovMX with your is-a.dev subdomain.

## What you need to do before you continue.

1. Have a ImprovMX account. If you don't have a ImprovMX account, please go to [their site](https://improvmx.com) and make a account.
2. You should have already forked the [is-a.dev repository](https://github.com/is-a-dev/register). If you haven't forked the repository, please make one by using [this link](https://github.com/is-a-dev/register/fork).

## Making the file.

First go to the fork you've made, then go into the `domains` directory and make a file. The file should be named like this: `subdomain.json`. (Replace `subdomain` with the subdomain name you want of course.)

After you've made the file, you should put in the file this:
```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**After you have made the file, you should make a pull request to the [is-a.dev repository](https://github.com/is-a-dev/register).**

## Configuring

After it has been merged, it should be automatically recognized and should start working. If you haven't configured it beforehand, please go to the [ImprovMX dashboard](https://app.improvmx.com/) and add the domain there.
