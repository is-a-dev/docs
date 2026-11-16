---
icon: rocket
label: Quick Start
route: /quickstart
order: 100
tags: [useful, guides]
---

# Quickstart Guide

## Requirements before starting

Before you start the process of making an is-a.dev domain, make sure you have the following:

1. You have a website that is at least somewhat complete. It should not be blank or have very little information.
2. Make sure the website is a personal website (like a portfolio or a blog that's software development related) or a non-commercial project that's software development related.
3. Make sure the website isn't for commercial purposes; if the website is for commercial purposes, we have the right to close the pull request. You can read our Terms of Service [here](https://is-a.dev/terms).

After you've made sure that you meet these requirements, we can continue with the process of making a is-a.dev domain.

## Making the is-a.dev domain

Now, to make the file in the first place before making a pull request, you have to fork [our repository](https://github.com/is-a-dev/register). You can click the link [here](https://github.com/is-a-dev/register/fork) to do so.

After you've forked our repository, you can start making the file for your domain. To make the file, enter your fork of our repository (which you should already be there), enter the `domains` directory, also known as a folder, and create the file from there.

You may be wondering, "How should I name the file?" The filename should be the domain name you want in lowercase followed by the JSON extension (.json) at the end of the filename, so it would be something like this: `subdomain.json` (Replace `subdomain` with the name you want to register, of course). For more information about what filenames are valid or invalid, click [here](https://docs.is-a.dev/domain-structure/#-filename-guidelines).

After you've finished with the filename, you can start making the file format of the JSON file. Depending on your hosting provider, we have guides for most hosting providers (like GitHub Pages, Cloudflare Pages and Vercel, just to name a few) accessible in our documentation, but for hosting providers that don't have a guide, you should pay attention to what records they provide. An example of a valid file format is the one listed below, though you can also check out the [Domain Structure](useful/domain-structure) section to see what records we support.

```json
{
    "owner": {
        "username": "your-github-username"
    },
    "records": {
        "CNAME": "example.org"
    }
}
```

!!!
You should replace the placeholder username with your own GitHub username and the placeholder records with the valid records your hosting provider gave while trying to connect the domain.
!!!

When you've made sure that you have the valid file format and the correct filename, you can now start making a pull request. If you aren't sure if the JSON format is valid, you can check with [jsonlint](https://jsonlint.com/).

### Making the pull request

Assuming you know how GitHub works, it should be easy for you to make a pull request to our repository. For those who don't know how to make one, you can check [this guide from GitHub's documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) on how to do it.

Before you create the pull request, make sure that you've read the pull request template and have completed it with the right information in order to save both your time and our (the maintainers') time.

Here is the PR template:

```md
<!--
YOU MUST FILL OUT THIS ENTIRE TEMPLATE FOR YOUR PR TO BE APPROVED!

DO NOT MODIFY OR REMOVE THIS TEMPLATE (INCLUDING REMOVING COMMENTS) OR YOUR PR WILL FAIL VALIDATION!
-->

# Requirements
<!-- Your domain MUST pass ALL the requirements below, otherwise it WILL BE DENIED. -->
<!-- Change each checkbox to [x] (all lowercase, with no spaces between the brackets) to mark it as completed. -->
<!-- Do not modify anything in this section other than the checkboxes, or your PR will fail validation. -->

- [ ] <!-- TOS --> I **agree** to the [Terms of Service](https://is-a.dev/terms). <!-- Your request MUST follow the TOS to be approved. -->
- [ ] <!-- DOMAIN_STRUCTURE --> My file is following the [domain structure](https://docs.is-a.dev/domain-structure/). <!-- Your file is in the domains directory, the name is valid, it is JSON format, etc. -->
- [ ] <!-- WEBSITE_REACHABLE --> My website is **reachable** and **completed**. <!-- We do not permit simple "Hello, world!" or simply copied template websites with minimal changes. -->
- [ ] <!-- SOFTWARE_RELATED --> My website is **software development** related. <!-- We do not accept websites such as gaming, courses, AI agents/chatbots, etc. NOTE: Only your root subdomain needs to meet this requirement. -->
- [ ] <!-- NON_COMMERCIAL --> My website is **not for commercial use**. <!-- Your website's purpose should not be to generate any form of revenue or profit. (e.g. a business) -->
- [ ] <!-- CONTACT_INFO --> I have provided sufficient contact information in the `owner` key. <!-- Provide your email in the `email` field or another platform (e.g. Twitter or Discord) for contact. -->
- [ ] <!-- WEBSITE_LINK --> I have provided a link to my website below. <!-- This step is required for your PR to be approved. -->

# Website Preview
<!-- Provide a LINK (not a screenshot) to your website below between the start/end markers. -->
<!-- This should be a LINK to the existing domain your website is on, NOT the is-a.dev domain you're applying for. (e.g. https://abc.vercel.app, https://abc.github.io) -->

<!-- WEBSITE_PREVIEW_START -->
<!-- WEBSITE_PREVIEW_END -->

# Website Purpose
<!-- Please tell us the purpose or motive behind your website in between the start/end markers. For example, it is a portfolio website, etc. -->

<!-- WEBSITE_PURPOSE_START -->
<!-- WEBSITE_PURPOSE_END -->
```

!!!danger
Please don't replace the pull request template with something else, since that could result in your pull request being closed instantly when a maintainer sees it. Please also add a preview of your website with both the link to your website and a screenshot of your website in the pull request description.
!!!

When you've completed it, you can create the pull request and wait for the maintainers to review it. Make sure to also check the pull request from time to time to see if there's any changes that need to be made.


## What do I do now?

When your pull request has been merged by a maintainer, you have to make sure that you've connected the domain with your website, or else it won't work. Go to your website's settings and add the domain from there to make sure you've added it. After you've connected the domain, you are good to go! Now you can enjoy your is-a.dev domain. If you have any questions then you can either make a GitHub issue on our main repository or [join our Discord server](https://discord.gg/is-a-dev-830872854677422150) and ask there. You can also read our [FAQ](useful/faq) since we should have most of the common questions answered there.
