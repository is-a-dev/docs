---
icon: question
label: FAQ
route: /faq
tags: useful
---

# 📘 Frequently Asked Questions (FAQ)

## Which DNS record types are supported?

We support the following DNS record types:

* `A`
* `AAAA`
* `CAA`
* `CNAME`
* `DS`
  *Note: Must be used alongside `NS` records for DNSSEC.*
* `MX`
* `NS`
  *Note: Only approved in specific cases. See [Who can use NS records?](#who-can-use-ns-records) for details.*
* `SRV`
* `TLSA`
* `TXT`
* `URL`
  *Note: This is not a true DNS record. It uses Cloudflare’s redirection service.*

---

## Why does my domain still redirect to the is-a.dev homepage?

This usually happens due to browser caching. [Clear your browser cache](https://support.google.com/accounts/answer/32050) and try again.

---

## Can I use a CNAME record with other record types?

No, unless the domain is proxied. A `CNAME` cannot be combined with other record types (`A`, `MX`, `TXT`, etc.) in the same record set. For exceptions and setup instructions, see [Proxying Your Domain](https://docs.is-a.dev/domain-structure/#proxied-optional).

---

## How long does it take for my pull request to be merged?

We're a team of volunteers, and is-a.dev is a side project for us, so review times can vary. We’ll get to your PR as soon as we can. To potentially speed things up, share your PR link in [#pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) on our [Discord server](https://discord.gg/is-a-dev-830872854677422150).

---

## Which platforms or services are supported?

While you can use almost any service, these are the most commonly used with is-a.dev:

* Cloudflare Pages
* GitHub Pages
* Netlify
* Railway
* Vercel

---

## Can I create nested subdomains (e.g., `sub.example.is-a.dev`)?

Yes! You can nest subdomains as deeply as you'd like. To create one, name your file like `blog.example.json`. You **must own** `example.is-a.dev` to register `blog.example.is-a.dev`.

---

## I get an SSL error using GitHub Pages. How do I fix it?

Go to your GitHub Pages settings for your repository and **enable "Enforce HTTPS"**. This resolves most SSL issues.

---

## Can I become a maintainer or join the is-a.dev team?

We don’t accept direct applications. Team members are **handpicked**, often based on community involvement and support activity. Even then, it does **not guarantee** a position.

---

## I accidentally leaked sensitive data in my PR, what can I do?

* If **your PR has not been merged**, contact us immediately:

  * Email: [security@is-a.dev](mailto:security@is-a.dev)
  * Discord: [@williamharrison](https://discord.com/users/853158265466257448)

* If your PR **has already been merged**, we cannot retroactively remove it.

---

## Can I use my domain for a Minecraft server?

Yes, use an `A` record and an `SRV` record.
Refer to this [Namecheap article](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) for guidance.

> ⚠️ Root subdomains (e.g., `yourname.is-a.dev`) **must relate to software development** as required in our [Terms of Service](https://is-a.dev/terms).
> Use a *nested* subdomain (e.g., `mc.yourname.is-a.dev`) for Minecraft.

---

## Who can use NS records?

We **allow** NS records only when:

* The standard DNS record types we support aren’t sufficient.
  ✅ You must provide clear, technical justification.
* A DNS provider (e.g., Aternos) requires NS delegation.
  ✅ You must provide documentation.

We **do not allow** NS records for:

* Convenience or ease of use
* Unverifiable or unsupported claims
* Non-functional or placeholder purposes
* Security concerns or abuse risk

> ⚠️ **We reserve the right to deny any NS request at our discretion.**

---

## Why are NS records restricted?

NS records give full control over DNS for a subdomain. That opens the door to misuse, abuse, and security concerns. To protect the community and domain integrity, we must be strict about who receives NS delegation.

---

## How can I update or delete my is-a.dev subdomain?

Follow these steps:

1. **Review the [documentation](https://docs.is-a.dev) and [ToS](https://is-a.dev/terms)**.
2. **Open your JSON file** (in `/domains/your-subdomain.json`).
3. **Make your changes** (or delete the file if you’re removing your domain).
4. **Commit the changes** to your fork.
5. **Push** them to your GitHub fork.
6. **Open a pull request** from your forked repo.
7. **Wait for approval and merging** by a maintainer.

> 💡 Keep an eye on your pull request, we may request changes before merging.
