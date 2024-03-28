# Setting up Discord domain connection with your is-a.dev domain

## Get your verification string

1. Open your settings

<img src="../img/discord_step_1.png" height="259">

2. Open the "Connections" section

<img src="../img/discord_step_2.png" height="259">

3. Press the "View more" button

<img src="../img/discord_step_3.png" height="259">

4. Click on the domain button (a globe icon)

<img src="../img/discord_step_4.png" height="259">

5. In the field that appears type your is-a.dev domain name

<img src="../img/discord_step_5.png" height="259">

6. Copy the verification string

<img src="../img/discord_step_6.png" height="259">

## Create the domain file

Create a JSON file inside the `domains` directory (`domains/_discord.<subdomain>.json`) with the following content:

```json 
{
    "owner": {
        "username": "<github-username>",
        "email": "email@address"
    },
    "record": {
        "TXT": "<discord-verification-string>"
    }
} 
```

# Configuration
After your pull request has been merged, repeat the steps to get the verification string and press the "Verify" button.
If it shows any error such as "Unable to verify your domain", try waiting a few minutes, the DNS change might not have reached discord DNS server yet