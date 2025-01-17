---
icon: file-code
route: /domain-structure
tags: useful
---
# Domain Structure
To register a subdomain, you need to create a new JSON file in the `domains` directory through a pull request. For example, to register `example.is-a.dev`, you would create a file named `example.json` in the `domains` directory. The full path would be `domains/example.json`.

## Filename

**Note**: You can include `.` (dots) in your filename to register a sub-subdomain (e.g., `blog.example.is-a.dev`). However, each segment of your subdomain must meet the following criteria:

The filename:

- Must be alphanumeric, in lowercase, with dashes as separators.
- Must be at least 1 character.
- Must have a `.json` file extension.

### Examples of Invalid Filenames
- `.json` (filename is less than 1 character)
- `A.json` (filename contains uppercase letters)
- `a..json` (filename contains consecutive dots)
- `.a.json` (filename starts with a dot)
- `a .json` (filename contains a space)
- `a$.json` (filename contains a non-alphanumeric character)
- `a.json.json` (filename contains more than one `.json` extension)
- `a.is-a.dev.json` (filename contains `.is-a.dev`)

### Examples of Valid Filenames
All the filenames below meet all the criteria. The reason in parentheses is just an example of one of the criteria they meet.

- `a.json` (at least 1 character long)
- `example.json` (alphanumeric and in lowercase)
- `blog.example.json` (includes dots to register a sub-subdomain)
- `my-blog.json` (uses dashes as separators, which is recommended)

**NOTE:** To stop a person from having a monopoly over one-lettered subdomains, we limit everyone to only one one-lettered subdomain.

### Example JSON File
`domains/docs.json`

```json
{
  "description": "Documentation website for is-a.dev",
  "repo": "https://github.com/is-a-dev/docs",
  "owner": {
    "username": "is-a-dev",
    "email": "admin@is-a.dev"
  },
  "record": {
    "CNAME": "is-a-dev-docs.pages.dev"
  },
  "proxied": true
}
```

## Structure

### owner (required)
You need to specify some information about yourself here. This is so that you can be contacted if required.
In the owner object, the fields username and email are required. You can add more information in this object if you want.
```json
{
  "owner": {
    "username": "github-username"
  }
}
```

### description
Describe your domain name and your usage. This is purely for documentation purpose and is optional.

### repo
This is a link to your website repository or your github account. This is purely for documentation purpose and is optional.

### record (required)
This section is where you specify the DNS records.

You can see a list of supported types [here](./faq#which-records-are-supported).

Below are some examples for the given record types:

- **CNAME** record: This must be a hostname (`something.tld`). It cannot be used in conjunction with any other record types. This is typically used to map your domain to a specific server.
```json
{
  "record": {
    "CNAME": "github-username.github.io"
  }
}
```
- **A** record: This must be a list of IPv4 addresses. These addresses point your domain to a specific server.
```json
{
  "record": {
    "A": [
      "192.0.2.1",
      "198.51.100.1",
      "203.0.113.1"
    ]
  }
}
```
- **AAAA** record: This must be a list of IPv6 addresses. Like the A record, these addresses point your domain to a specific server.
```json
{
  "record": {
    "AAAA": [
      "2001:0db8:85a3:0000:0000:8a2e:0370:7334",
      "2001:0db8:85a3:0000:0000:8a2e:0370:7335",
      "2001:0db8:85a3:0000:0000:8a2e:0370:7336"
    ]
  }
}
```
- **URL** record: This redirects your domain to another URL.
```json
{
  "record": {
    "URL": "https://example.com"
  }
}
```
- **MX** record: This must be a list of hostnames. These hostnames specify the mail servers that handle emails for your domain.
```json
{
  "record": {
    "MX": [
      "mx1.improvmx.com",
      "mx2.improvmx.com"
    ]
  }
}
```
- **TXT** record: This can be either a single string or a list of strings. TXT records are often used for various purposes, such as verifying domain ownership and ensuring email security.
```json
{
  "record": {
    "TXT": "Hello World!"
  }
}
```
```json
{
  "record": {
    "TXT": ["Hello", "World!"]
  }
}
```
- **NS** record: This must be a list of hostnames. These hostnames specify the authoritative DNS servers for your domain.
```json
{
  "record": {
    "NS": [
      "ns1.example.com",
      "ns2.example.com"
    ]
  }
}
```
Note: Please refer to the [frequently asked questions](https://docs.is-a.dev/faq/) for clarification on what or who we allow NS records for. If you want a example on what we want as the reasonings, you can [checkout this PR](https://github.com/is-a-dev/register/pull/16758).

- **SRV** record: This must be a list of service records. Each record specifies the priority, weight, port, and target for a service on your domain. SRV records are often used for services such as VoIP, messaging, and more.
```json
{
  "record": {
    "SRV": [
      {
        "priority": 10,
        "weight": 5,
        "port": 8080,
        "target": "srv.example.com"
      },
      {
        "priority": 20,
        "weight": 10,
        "port": 9090,
        "target": "srv2.example.com"
      }
    ]
  }
}
```
- **CAA** record: This must be a list of Certification Authority Authorization (CAA) records. Each record specifies the authority permitted to issue SSL certificates for your domain, with fields for `flags`, `tag`, and `value`.
```js
{
  "record": {
    "CAA": [
      {
        "flags": 0,
        "tag": "issue",
        "value": "letsencrypt.org"
      },
      {
        "flags": 0,
        "tag": "issuewild",
        "value": "comodoca.com"
      }
    ]
  }
}
```

### proxied (*optional*)
Enable Cloudflare proxy for your domain. Disabled by default. To enable it, add this line of code:
```json
"proxied": true
```
