---
icon: file-code
route: /domain-structure
tags: useful
---

# Domain Structure

To register a subdomain, submit a pull request with a new JSON file in the `domains` directory.
For example, to register `example.is-a.dev`, create a file named `example.json` in `domains/`:

```
domains/example.json
```

---

## 📁 Filename Guidelines

To register a nested subdomain like `blog.example.is-a.dev`, use dots (`.`) in the filename:
`blog.example.json`

Each part of the filename (i.e., each subdomain label) must follow these rules:

* Must be **alphanumeric and lowercase**. Dashes (`-`) are allowed as separators, but **not consecutively** (e.g., `--` is invalid).
* Minimum of **1 character**, maximum of **244 characters** (excluding `.json`).
* Each label (segment between dots) must be **≤ 63 characters**.
* File must **end with `.json`**.
* **Must not contain `is-a.dev`**.
* **Must not begin with a dot**, or contain spaces or invalid characters.

### ❌ Invalid Filenames

| Filename                      | Issue                               |
| ----------------------------- | ----------------------------------- |
| `.json`                       | Empty filename                      |
| `A.json`                      | Uppercase letters                   |
| `a..json`                     | Consecutive dots                    |
| `.a.json`                     | Starts with a dot                   |
| `a .json`                     | Contains a space                    |
| `a$.json`                     | Non-alphanumeric character          |
| `a.json.json`                 | Multiple extensions                 |
| `a.is-a.dev.json`             | Contains reserved string `is-a.dev` |
| `a--a.json`                   | Consecutive dashes                  |
| `blog._a.json`                | Label starts with an underscore     |
| `abc123.aaaaaaaa...aaaa.json` | Label exceeds 63 characters         |
| `very.long.filename...json`   | Filename exceeds 244 characters     |

### ✅ Valid Filenames

| Filename                       | Why It's Valid                      |
| ------------------------------ | ----------------------------------- |
| `a.json`                       | Minimum 1 character                 |
| `example.json`                 | Lowercase and alphanumeric          |
| `blog.example.json`            | Nested subdomain                    |
| `my-blog.json`                 | Uses dashes correctly               |
| `mail._domainkey.example.json` | Underscore is not in the root label |
| `_vercel.example.json`         | Valid underscore usage              |
| `abc123.json`                  | Alphanumeric                        |

> **Note:** Users may only register *one* single-letter subdomain to prevent domain squatting.

---

## 🧾 Example JSON File

`domains/docs.json`:

```json
{
  "owner": {
    "username": "is-a-dev",
    "email": "admin@is-a.dev"
  },
  "records": {
    "CNAME": "is-a-dev-docs.pages.dev"
  },
  "proxied": true
}
```

---

## JSON Structure

### 🔐 `owner` (required)

Provides contact information. Required fields:

* `username`: Your GitHub username.

Example:

```json
{
  "owner": {
    "username": "your-github-username"
  }
}
```

---

### 🌐 `records` (required)

Specify your domain's DNS records.

See all supported record types in the [FAQ](./faq#which-records-are-supported).

#### Record Type Examples

* **A**
  Points to IPv4 addresses:

  ```json
  "A": ["192.0.2.1", "198.51.100.1"]
  ```

* **AAAA**
  Points to IPv6 addresses:

  ```json
  "AAAA": ["2001:db8::1", "2001:db8::2"]
  ```

* **CAA**
  Controls which CAs can issue certificates:

  ```json
  "CAA": [
    { "flags": 0, "tag": "issue", "value": "letsencrypt.org" }
  ]
  ```

* **CNAME**
  Points to another hostname:

  ```json
  "CNAME": "your-site.example.com"
  ```

* **DS**
  DNSSEC delegation signer:

  ```json
  "DS": [
    {
      "key_tag": 2371,
      "algorithm": 13,
      "digest_type": 2,
      "digest": "..."
    }
  ]
  ```

* **MX**
  Email servers for your domain:

  Simple form:

  ```json
  "MX": [
    "mx1.example.com",
    "mx2.example.com"
  ]
  ```

  With priority:

  ```json
  "MX": [
    { "target": "mx1.example.com", "priority": 10 },
    { "target": "mx2.example.com", "priority": 20 }
  ]
  ```

* **NS**
  Delegates DNS to other nameservers:

  ```json
  "NS": ["ns1.example.com", "ns2.example.com"]
  ```

  > Refer to the [FAQ](https://docs.is-a.dev/faq/#who-can-use-ns-records) for guidance on valid use cases.

* **SRV**
  Defines service records:

  ```json
  "SRV": [
    {
      "priority": 10,
      "weight": 5,
      "port": 8080,
      "target": "service.example.com"
    }
  ]
  ```

* **TLSA**
  Validates a TLS/SSL certificate:

  ```json
  "TLSA": [
    {
      "usage": 1,
      "selector": 1,
      "matching_type": 1,
      "certificate": "..."
    }
  ]
  ```

* **TXT**
  Used for verification and other metadata:

  Single string:

  ```json
  "TXT": "Some verification text"
  ```

  List format:

  ```json
  "TXT": ["part1", "part2"]
  ```

* **URL**
  Redirects your subdomain to a URL:

  ```json
  "URL": "https://example.com"
  ```

---

### ☁️ `proxied` (optional)

Enable Cloudflare proxy:

```json
"proxied": true
```

---

### 🔁 `redirect_config` (optional)

Custom redirect paths for your domain:

```json
"redirect_config": {
  "custom_paths": {
    "/github": "https://github.com/is-a-dev"
  },
  "redirect_paths": true
}
```

> See full example: [`william.json`](https://github.com/is-a-dev/register/blob/main/domains/william.json)
