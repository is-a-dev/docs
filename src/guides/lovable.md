---
order: 150
icon: /media/lovable/icon.svg
label: Lovable
tags: guides
---

## Setting up Lovable project with an is-a.dev subdomain

This guide will walk you through the process of making your Lovable Project work on is-a.dev subdomains. Currently Lovable doesn't intergrate directly with is-a.dev, so we have to use GitHub as a proxy with [Cloudflare Pages](/guides/cloudflare-pages) to make this work. We will use the user `doughmination` for this example.

### Connect your project to GitHub

1. Open your project's `More` page, `Settings` tab and navigate to the `Git` tab.
    ![](../media/lovable/l/step1.png)

2. Click the `GitHub` button, and `Add Connection`, then `Add Account`.
    ![](../media/lovable/l/step2.png) ![](../media/lovable/l/step2b.png)
Note: If you login with GitHub, you may already have your account connected

3. Once you connect the account, click `Connect`, which connect to a GitHub repository. 
    ![](../media/lovable/l/step3.png)

4. You can see it as a recent Private repository. Make a note of the project's name.
    ![](../media/lovable/l/step4.png)



### Connect GitHub to Cloudflare Pages

1. Open Cloudflare and under `Build`, press `Compute`, then `Workers & Pages`.
    ![](../media/lovable/cf/step1.png)

2. Click `Create Application`, and then access Pages via `Continue to Pages`.
    ![](../media/lovable/cf/step2.png) ![](../media/lovable/cf/step2b.png)

3. Press `Import an existing Git repository` to access your GitHub account.
    ![](../media/lovable/cf/step3.png)

4. Connect GitHub.
    ![](../media/lovable/cf/step4.png) ![](../media/lovable/cf/step4b.png)

5. Select your project's name, so we can auto-pull from source.
    ![](../media/lovable/cf/step5.png)

6. Configure the build to the below settings.
    ![](../media/lovable/cf/step6.png) ![](../media/lovable/cf/step6b.png)

7. Press the `Save and Deploy` button, and carry on the flow.

After the page finishes building, you can now make a PR, for this, please see the [Cloudflare Pages](/guides/cloudflare-pages) guide.