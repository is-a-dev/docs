---
icon: rocket
label: Quick Start
route: /quickstart
tags: useful
---

# Requirements before starting

Before you start the process of making a is-a.dev domain, make sure you have the following:
    1. You have a website that is at least somewhat complete. It should not be blank or have very little information.
    2. Make sure the website is a personal website (like a portfolio or a blog that's software development related) or a non-commercial project that's software development related.
    3. Make sure the website isn't for commercial purposes; if the website is for commercial purposes, we have the right to close the pull request. You can read our Terms of Conditions [here](https://is-a.dev/terms).
    
After you've made sure that you meet these requirements, we can continue with the process of making a is-a.dev domain.

# Making the is-a.dev domain

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

## Making the pull request

Assuming you know how GitHub works, it should be easy for you to make a pull request to our repository. For those who don't know how to make one, you can check [this guide from GitHub's documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) on how to do it.

Before you create the pull request, make sure that you've read the pull request template and have completed it with the right information in order to save both your time and our (the maintainers') time.

!!!danger
Please don't replace the pull request template with something else, since that could result in your pull request being closed instantly when a maintainer sees it. Please also add a preview of your website with both the link to your website and a screenshot of your website in the pull request description.
!!!

When you've completed it, you can create the pull request and wait for the maintainers to review it. Make sure to also check the pull request from time to time to see if there's any chances that need to be made.


# What do I do now?

When your pull request has been merged by a maintainer, you have to make sure that you've connected the domain with your website, or else it won't work. Go to your website's settings and add the domain from there to make sure you've added it. After you've connected the domain, you are good to go! Now you can enjoy your is-a.dev domain. If you have any questions then you can either make a GitHub issue on our main repository or [join our Discord server](https://discord.gg/is-a-dev-830872854677422150) and ask there. You can also read our [FAQ](useful/faq) since we should have most of the common questions answered there.