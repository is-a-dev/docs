---
icon: /media/discord.svg
label: Discord Domain Connection
tags: guides
---

# Setting up Discord domain connection with your is-a.dev subdomain

## Get your verification string

1. Open your Discord app and press `Settings`.
   ![](../media/discord/step_1.png)

2. Open the `Connections` section.
   ![](../media/discord/step_2.png)

3. Press the `View more` button.
   ![](../media/discord/step_3.png)

4. Click on the domain button (the globe icon).
   ![](../media/discord/step_4.png)

5. In the field that appears type your is-a.dev domain name (e.g. `example.is-a.dev`).
   ![](../media/discord/step_5.png)

6. Copy the verification string.
   ![](../media/discord/step_6.png)

### Create your domain file

Create a JSON file inside the `domains/` directory called `domains/_discord.example.json` with the following content:

```json
{
    "owner": {
        "username": "your-github-username"
    },
    "records": {
        "TXT": "discord-verification-string"
    }
}
```

**Note:** Don't forget the comma right above the `"records"` key!

## Configuration

After your pull request has been merged, repeat steps 1-5 and press the `Verify` button.
If it shows any error such as `Unable to verify your domain`, try waiting a few minutes (sometimes up to 24 hours) as the DNS might not have propagated yet.
