---
order: 900
label: Other services
icon: server
tags: guides
---

# Setting up other services with is-a.dev

## Setting up records

Read the [domain file structure](../useful/domain-structure) and set up the records accordingly.

## Configuring your server

After the pull request is merged, configure your server (apache, nginx, etc.) to work with `subdomain.is-a.dev`. If you are unsure how to configure your server, you can [create an issue](https://github.com/is-a-dev/register/issues/new/choose) for support.

You should also include `subdomain.is-a.dev` in your ssl certificate to get rid of certificate errors.
