## Register your is-a.dev subdomain to use hosting by is-a-dev

## First register a domain using the dashboard
You can find the guide on how to do that [here](https://is-a.dev/docs/dashboard)
and once your on the records page choose hosting by is-a.dev
or you can manualy add theese records to your exsisting subdomain 
```json
 "record": {
        "A": ["217.174.245.249"],
        "MX": ["hosts.is-a.dev"],
        "TXT": "v=spf1 a mx ip4:217.174.245.249 ~all"
    }
```
## After your PR is merged
You should have gotten an email with your credentials to access your FTP server
You can access it by going to [FTP editor](https://www.net2ftp.com/index.php?protocol=FTP&ftpserver=hosts.is-a.dev&ftpserverport=21&sshfingerprint=&language=en&skin=shinra&ftpmode=automatic&passivemode=yes&viewmode=list&sort=&sortorder=&state=login_small&state2=bookmark&go_to_state=browse&go_to_state2=main&directory=&entry=/) and entering in your login credentials
If you want to link your subdomain with your subdomain you can follow this [video](https://www.loom.com/share/f5ed7997364a435caa126ae7fd1d0485?sid=bd4eeb3a-341c-4262-86d3-11d1c6fa6070)
Also if you need to change your password then where you add your discord TXT record is also where you can set the password for the FTP and SMTP server and enable SMTP


