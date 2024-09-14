# Setting up Vercel with is-a.dev subdomain

This guide will walk you through the process of setting up a Vercel site and pointing your is-a.dev subdomain to it.

## Make sure you have a Vercel site.
If you haven't made a Vercel site, make sure to make one. Follow the instructions in [Vercel's Docs](https://vercel.com/docs/getting-started-with-vercel).

## Creating the domain files.
First, go to your Vercel dashboard, then go to your project, then go to Custom Domains and put in there the is-a.dev subdomain you want.

**You will need to make two files to ensure this proccess goes smoothly**. We will go in order for this section.

1. Make a file for Vercel TXT verification.
When connecting the domain, you will be greeted with a TXT verification. To make the file for this one it should be `_vercel.subdomain.json` in the **domains directory** (replace subdomain with the domain you want of course) and the file should be like this (You can leave email field blank as long as you have another social, but **DON'T REMOVE THE FIELD**.):
```json
{
  "owner": {
    "username": "insertusername",
    "email": ""
    "discord": "insertdiscordid"
  },
  "record": {
    "TXT": "inserttxtstring"
  }
}
```
**DON'T MAKE A PR YET**, we still have to make another file. If you were to make a PR until this point, we will reject your domain since you are trying to make a nested subdomain on a subdomain you don't own yet. Please go to the next step.

2. Make a file for the main domain.
Now you need to make a file for the main domain, we have 2 ways to do it: CNAME and A records. We'll have 2 different files for these and explain what restricions or stuff you need to do.

Make the file `subdomain.json` in the **domains directory** (replace subdomain with the domain you want of course) and put in the file one of these types:
**CNAME record**: If you are using CNAME record you don't have to give a preview as you are using the site as the CNAME, but you can't use other record. (Like MX and TXT records)
```json
{
  "owner": {
    "username": "insertusername",
    "email": "",
    "discord": "insertdiscordid"
  },
  "record": {
    "CNAME": "domainname.vercel.app"
  }
}
```
**A record**: If you are using A record, you would need to give a preview either a link via the comment of the PR or put it in the description, or you can give a screenshot of your website.
```json
{
  "owner": {
    "username": "insertusername",
    "email": "",
    "discord": "insertdiscordid"
  },
  "record": {
    "A": ["76.76.21.21"]
  }
}
```
## Make your PR.
After you have made these 2 files, you can now make a PR (Pull Request) to the main repo.
