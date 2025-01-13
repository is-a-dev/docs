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
    - Note: These can only be used in combination for NS records, which are used for DNSSEC.
- MX
- NS
    - Note: These are only given out in specific cases. Refer to [`Who can use NS records?`](#who-can-use-ns-records) for more information.
- SRV
- TXT
- URL
    - Note: These records use Cloudflare for redirection, it is not a real DNS record type.

## Why does my domain still redirect to the is-a-dev website?
This usually occurs due to the cache of your browser becoming invalid and [clearing your browser's cache](https://support.google.com/accounts/answer/32050) should solve this issue.

## Can I use a CNAME record with any other records?
You cannot request a subdomain nor submit changes containing a CNAME with any other records (A, AAAA, MX, TXT, etc...)

## How long will it take for my PR to get merged?
When we get into it. We always want you to wait for as short as possible. But maintainers cannot always be online. We have school and work, this is just a side project. Just be patient and we'll get to it as soon as possible! For a chance for a quicker review, send your PR in [#⁠pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) on our [Discord server](https://discord.gg/is-a-dev-830872854677422150).

## Which services do you support?
We support nearly all services, however these are the main services people use with is-a.dev:

- Cloudflare Pages
- GitHub Pages
- Netlify
- Railway
- Vercel

## Can I create nested subdomains? (sub-sub domains)
Yes, you can! Simply create a file such as `blog.example.json` and follow the same guidelines as you would while registering `example.json`. Please note in order to have `blog.example.is-a.dev`, you must also own `example.is-a.dev`.

## How can I edit my domain?
You can edit your domain's JSON file and submit a pull request to edit your domain.

## How can I delete my domain?
You can delete your domain's JSON file and submit a pull request to delete your domain.

## I keep getting a SSL error while using GitHub Pages, how do i fix this?
You need to go to your GitHub Pages settings on your website repository (likely called something like `github-username.github.i>`) and make sure the `Enforce HTTPS` option is enabled to avoid this error.

## Can I be a maintainer/join the team?
No, we handpick every member of our team. You can increase your chances of being chosen by helping out people in our help forums.

## I have accidentally leaked sensitive information in my PR, how can I get my PR deleted?
If your PR **has not been merged**, you can email [security@is-a.dev](mailto:security@is-a.dev) or DM [williamharrison on Discord](https://discord.com/users/853158265466257448). If your PR has been merged already, then there is nothing we can do about it unfortunately.

## Can I use my domain for a Minecraft server?
Yes, you can. You can use an A record combined with an SRV record for this.

Refer to [this article](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) by Namecheap for support.

## Who can use NS records?
We allow NS records for the following reasons and use-cases:

- Users who require a private zone, as they are using their home IP address through **an `A` OR `AAAA` record** behind a proxy service such as Cloudflare. **You MUST provide evidence of usage for this reasoning to be approved.**
- When a third-party service (e.g. Aternos, Wix or Squarespace) mandates specific NS records and you are unable to manage DNS records directly under that domain. Approval requires:
  - Documentation or evidence from the third-party service explicitly stating this requirement.
  - Proof that no alternative DNS configuration (CNAME, A records, etc.) can achieve the same result.

We do not permit NS records for:

- Convenience-only setups: Where alternatives such as A, AAAA, or CNAME records are sufficient.
- Non-operational purposes: Vanity configurations, aesthetic setups, or speculative use.
- Unverifiable claims: Any setup lacking clear and concrete evidence of necessity.
- Misleading configurations: Attempts to misrepresent ownership, mislead users, or impersonate another entity.
- Security risks: Configurations that introduce vulnerabilities, such as delegating to untrusted or unreliable servers.

***We reserve the right to deny NS records at our discretion, no matter the reasoning.***

## Why are you so strict with NS records?
We have to be strict with who we delegate NS records to as they allow the end-user to do basically *whatever they want* with their subdomain.

As you can probably imagine, this can open the door to a lot of abuse, which is why are they are not freely available to everyone.

If we could, we would delegate NS records to everyone that wanted them, however we are not in a perfect world, so unfortunately we cannot.

## How can I make changes to my is-a.dev subdomain?
1. **Open your JSON file:** Navigate to the `domains` directory in your fork and open the JSON file corresponding to your subdomain (`domains/subdomain.json`).
2. **Make your changes:** Edit the JSON file (or delete) to reflect the changes you want to make.
3. **Commit your changes:** Once you've made your changes, commit them to your fork.
4. **Push your changes:** Push your changes to your forked repository on GitHub.
5. **Submit a Pull Request:** Go to your forked repository on GitHub and open a pull request.
6. **Wait for your PR to be merged:** After you have submitted your pull request, wait for it to be reviewed and merged. Once your pull request has been merged, your changes should be live!

**Note:** Make sure to monitor your PR for reviews in case some changes are requested.
