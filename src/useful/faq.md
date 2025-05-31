---
icon: question
label: FAQ
route: /faq
tags: useful
---
# Frequently Asked Questions (FAQ)

## Which records are supported?

- A
- AAAA
- CAA
- CNAME
- DS
    - Note: These can only be used in combination with NS records, which are used for DNSSEC.
- MX
- NS
    - Note: These are only given out in specific cases. Refer to [`Who can use NS records?`](#who-can-use-ns-records) for more information.
- SRV
- TLSA
- TXT
- URL
    - Note: These records use Cloudflare for redirection, it is not a real DNS record type.

## Why does my domain still redirect to the is-a.dev website?
This usually occurs due to the cache of your browser becoming invalid and [clearing your browser's cache](https://support.google.com/accounts/answer/32050) should solve this issue.

## Can I use a CNAME record with any other records?
You cannot request a subdomain nor submit changes containing a CNAME with any other records (A, AAAA, MX, TXT, etc...) unless the domain is proxied. For information on how to proxy a domain, see [proxying your domain](https://docs.is-a.dev/domain-structure/#proxied-optional).

## How long will it take for my pull request to get merged?
When we get to it. We always try to shorten users' wait time as much as possible; however, maintainers have lives and cannot always be online. We have school and work; this is just a side project. Remember that all the maintainers are volunteers. Be patient and we'll get to it as soon as possible! For a chance of a quicker review, send your your pull request link in [#⁠pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) on our [Discord server](https://discord.gg/is-a-dev-830872854677422150).

## Which services do you support?
We support nearly all services, however these are the main services people use with is-a.dev:

- Cloudflare Pages
- GitHub Pages
- Netlify
- Railway
- Vercel

## Can I create nested subdomains? (sub-sub domains)
Yes, you can! Simply create a file such as `blog.example.json` and follow the same guidelines as you would while registering `example.json`. Please note in order to have `blog.example.is-a.dev`, you must also own `example.is-a.dev`. Additionally, you can nest subdomains as much as you can — `example.example.example.is-a.dev` is possible.

## I get an SSL error while using GitHub Pages, how do I fix this?
Visit your GitHub Pages settings on your website's repository (most likely labelled similar to `your-github-username.github.io`) and ensure the `Enforce HTTPS` option is enabled to avoid this error.

## Can I become a maintainer/join the is-a.dev staff team?
No, we handpick each member of the team. You can increase your chances of being chosen by helping out people in our help forums and channels. This alone, however, will not guarantee in any way a position in the team.

## I have accidentally leaked sensitive information in my PR, how can I get my PR deleted?
If your PR **has not been merged**, email [security@is-a.dev](mailto:security@is-a.dev) or DM [@williamharrison on Discord](https://discord.com/users/853158265466257448). If your PR has been merged already, then there is unfortunately nothing we can do about it.

## Can I use my domain for a Minecraft server?
Yes, you can. You can use an A record combined with an SRV record for this.

Refer to [this article](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) by Namecheap for support.

Please note that you may only do this on a *nested subdomain*, as root subdomains must be related to software development as is required in our [Terms of Service](https://is-a.dev/terms).

## Who can use NS records?
We permit NS records for the following reasons:

- The DNS record types we already support are not sufficient for your use case. **Evidence must be provided for your use case and why you require them.**
- When a provider (e.g. Aternos) requires NS delegation, where they maintain the DNS zone, not you. **Supporting documentation must be provided.**

We do not permit NS records for:

- Convenience-only setups: Where alternatives such as A, AAAA, or CNAME records are sufficient.
- Non-operational purposes
- Lack of evidence for need of use
- Misleading evidence
- Security risks

***We reserve the right to deny NS records at our discretion, no matter the reasoning.***

## Why are you so strict with NS records?
We have to be strict with who we delegate NS records to as they allow the end-user to essentially do *whatever they wish* with their subdomain.

As you can probably imagine, this opens the door to a lot of abuse, which is why they are not freely available to everyone.

## How can I make changes to or delete my is-a.dev subdomain?
1. **Read this documentation and our [ToS](https://is-a.dev/terms)**: This is so that you can ensure you fully understand the registration process, our requirements, and how to fully comply with our Terms of Service.
2. **Open your JSON file:** Navigate to the `domains` directory in your fork and open the JSON file corresponding to your subdomain (`domains/your-subdomain.json`).
3. **Make your changes:** Edit or delete the JSON file to reflect the changes you want to make.
4. **Commit your changes:** Once you've made your changes, commit them to your fork.
5. **Push your changes:** Push your changes to your forked repository on GitHub.
6. **Submit a pull request:** Navigate to your forked repository on GitHub and open a pull request.
7. **Wait for your PR to be merged:** After you have submitted your pull request, wait for it to be reviewed and merged. Once your pull request has been merged, your changes should be live!

**Note:** Make sure to monitor your PR for reviews in case some changes are requested by a maintainer.
