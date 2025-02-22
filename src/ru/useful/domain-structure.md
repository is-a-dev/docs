---
icon: file-code
route: /ru/domain-structure
tags: useful
---
# Структура доменного имени
Чтобы зарегистрировать субдоменное имя, Вам нужно создать новый файл JSON в каталоге `domains` через pull request (запрос). Например: Для регистрации `example.is-a.dev`, Вам нужно создать файл в каталоге `domains` с названием `example.json` - путь к файлу должен получиться `domains/example.json`.
Если Вы хотите зарегистрировать субдоменное имя, которое содержит символы, не относящиеся к латинским буквам, цифрам, точке, тире, и нижним подчеркиванием, (пример - любая буква русского алфавита) то Вам нужно конвертировать данные символы в Punycode. Например: Для регистрации `пример.is-a.dev`, то имя файла будет `xn--e1afmkfd.json`.

## Имя файла

**Дополнительно**: Вы можете добавить `.` (точки) в Ваше имя файла, чтобы зарегистрировать суб-субдоменное имя (пример: `blog.example.is-a.dev`). Но каждый сегмент вашего субдоменного имени должен соблюдать следующие критерии:

Имя файла:

- Должно содержать только: буквы латинского алфавита, цифры, тире как разделитель.
- Должно содержать как минимум 1 символ.
- Файл должен быть `.json`.

### Примеры неправильных имён файла
- `.json` (имя файла содержит менее одного символа)
- `A.json` (имя файла содержит заглавные буквы)
- `a..json` (имя файла содержит две или более рядом стоящие точки)
- `.a.json` (имя файла начинается с точки)
- `a .json` (имя файла содержит пробел)
- `a$.json` (имя файла содержит символ, не относящийся к буквам латинского алфавита, или к цифрам, или к тире)
- `a.json.json` (имя файла содержит более одного расширения файла `.json`)
- `a.is-a.dev.json` (имя файла содержит `.is-a.dev`)

### Примеры правильных имён файла
Все имена файлов в следующем списке соответствуют вышеупомянутой критерии. Причина, указанная в скобках, является примером одного из критериев, которым они соответствуют.

- `a.json` (имя файла содержит как минимум 1 символ)
- `example.json` (имя файла содержит только символы, относящиеся к прописным буквам латинского алфавита, или к цифрам, или к тире)
- `blog.example.json` (имя файла содержит точку, для того чтобы зарегистрировать суб-субдоменное имя)
- `my-blog.json` (имя файла использует тире как разделитель)

**ВАЖНО:** Чтобы предотвратить возможность того, что один пользователь может владеть значимой частью 1-символьных субдоменных имён, мы поставили ограничение: максимум одно 1-символьное субдоменное имя на пользователя.

### Пример файла JSON
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

## Структура

### owner (владелец) (обязательно)
Вам нужно заполнить информацию о себе здесь. По данной информации мы сможем связаться с Вами в случае необходимости.
В объекте "`owner`", поля "`username`" и "`email`" - обязательны. Вы можете добавить больше информации по Вашему желанию.
```json
{
  "owner": {
    "username": "github-username"
  }
}
```

### description (описание)
Describe your domain name and your usage. This is purely for documentation purpose and is optional.

### repo (репозиторий)
This is a link to your website repository or your github account. This is purely for documentation purpose and is optional.

### record (запись/записи) (обязательно)
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
```json
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
- **DS** record: This must be a list of Delegation Signer(DS) records. Each verifies the authenticity of the (subdomain) zone with field `key_tag`, `algorithm`, `digest_type` and `digest`.
```json
"DS": [{
      "key_tag": 2371,
      "algorithm": 13,
      "digest_type": 2,
      "digest": "C2074462471B81206F792AEC23469EF33DDC53538E8580DCCC92FD130C9A6096"
    }]
```

### proxied (прокси) (*необязательно*)
Enable Cloudflare proxy for your domain. Disabled by default. To enable it, add this line of code:
```json
"proxied": true
```

### ¹ - Discord является запрёщенным мессенджером на территории РФ.
