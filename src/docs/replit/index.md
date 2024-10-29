# Setting up Replit with your is-a.dev subdomain

## Creating a project
Follow the instructions in the [Replit Workspace Guide](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) on how to create a project.

<!-- You need replit core, since they have a limit to 3 workspaces on free account, and deployment needs to be purchased also -->
## Connect your repl to your is-a.dev subdomain
Since Replit Workspaces has changed alot, follow the instructions in the [Replit Deployment Custom Domains Guide](https://docs.replit.com/cloud-services/deployments/custom-domains). You may need the Replit Deployment subscription to do so

## Creating the domain file
After clicking the "Link a Domain" button on your Replit Deployment menu and already typed the domain, you will see this
![image](https://github.com/user-attachments/assets/32abb589-5fad-4383-8554-eebe005052e9)
(The example screenshot uses their own domain, `kaboom.thedevbird.com`. But in our case, it should be `<subdomain>.is-a.dev`)

Create a JSON file inside `domains` directory (`domains/<subdomain>.json`) with the following content:

<!-- They are now using TXT for verification, not just `replit-user=cupglassdev`. When deleted, you cant use it in replit -->
```json 
{
    "owner": {
        "username": "<github-username>",
        "email": "<email@address>",
        "twitter": "<twitter-username>"
    },
    "record": {
        "A": "<IP here, listed on the A Record>",
        "TXT": "<TXT value here, listed on the TXT Record>"
    }
} 
```

## Configuring
- After your pull request has been merged into the main repository you should be able to visit your new is-a.dev domain and it should show you your replit site,
if it doesn't then you have configured your domain wrong.
