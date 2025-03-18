---
icon: file-code
route: /domain-structure
tags: useful
---
# Structura Domeniului
Pentru a înregistra un subdomeniu, trebuie să creezi un nou fișier JSON în directorul `domains` printr-un pull request. De exemplu, pentru a înregistra `example.is-a.dev`, ar trebui să creezi un fișier numit `example.json` în directorul `domains`. Calea completă ar fi `domains/example.json`.

## Numele Fișierului

**Notă**: Poți include `.` (puncte) în numele fișierului pentru a înregistra un sub-subdomeniu (de exemplu, `blog.example.is-a.dev`). Cu toate acestea, fiecare segment al subdomeniului tău trebuie să îndeplinească următoarele criterii:

Numele fișierului:

- Trebuie să fie alfanumeric, cu litere mici și cu cratime ca separatori.
- Trebuie să aibă cel puțin 1 caracter.
- Trebuie să aibă extensia `.json`.

### Exemple de Nume de Fișiere Invalide
- `.json` (numele fișierului are mai puțin de 1 caracter)
- `A.json` (numele fișierului conține litere mari)
- `a..json` (numele fișierului conține puncte consecutive)
- `.a.json` (numele fișierului începe cu un punct)
- `a .json` (numele fișierului conține un spațiu)
- `a$.json` (numele fișierului conține un caracter non-alfanumeric)
- `a.json.json` (numele fișierului conține mai mult de o extensie `.json`)
- `a.is-a.dev.json` (numele fișierului conține `.is-a.dev`)

### Exemple de Nume de Fișiere Valide
Toate numele de fișiere de mai jos îndeplinesc toate criteriile. Motivul din paranteze este doar un exemplu al unuia dintre criteriile pe care le îndeplinesc.

- `a.json` (cel puțin 1 caracter lungime)
- `example.json` (alfanumeric și cu litere mici)
- `blog.example.json` (include puncte pentru a înregistra un sub-subdomeniu)
- `my-blog.json` (folosește cratime ca separatori, ceea ce este recomandat)

**NOTĂ:** Pentru a împiedica o persoană să monopolizeze subdomeniile cu o singură literă, limităm pe toată lumea la un singur subdomeniu cu o singură literă.

### Exemplu de Fișier JSON
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

## Structură

### owner (obligatoriu)
Trebuie să specifici aici câteva informații despre tine. Acest lucru este necesar pentru a putea fi contactat dacă este nevoie.
În obiectul owner, câmpurile username și email sunt obligatorii. Poți adăuga mai multe informații în acest obiect dacă dorești.
```json
{
  "owner": {
    "username": "github-username"
  }
}
```

### descriere
Descrieți numele domeniului și utilizarea acestuia. Acest lucru este doar în scop de documentare și este opțional.

### repo
Acesta este un link către repository-ul site-ului tău web sau către contul tău GitHub. Acest lucru este doar în scop de documentare și este opțional.

### record (obligatoriu)
Această secțiune este locul unde specifici înregistrările DNS.

Poți vedea o listă cu tipurile acceptate [aici](./faq#which-records-are-supported).

Mai jos sunt câteva exemple pentru tipurile de înregistrări date:

- **Înregistrare CNAME**: Aceasta trebuie să fie un nume de host (`ceva.tld`). Nu poate fi folosită împreună cu alte tipuri de înregistrări. Aceasta este de obicei folosită pentru a mapa domeniul tău către un server specific.
```json
{
  "record": {
    "CNAME": "github-username.github.io"
  }
}
```
- **Înregistrare A**: Aceasta trebuie să fie o listă de adrese IPv4. Aceste adrese direcționează domeniul tău către un server specific.
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
- **Înregistrare AAAA**: Aceasta trebuie să fie o listă de adrese IPv6. La fel ca înregistrarea A, aceste adrese direcționează domeniul tău către un server specific.
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
- **Înregistrare URL**: Aceasta redirecționează domeniul tău către un alt URL.
```json
{
  "record": {
    "URL": "https://example.com"
  }
}
```
- **Înregistrare MX**: Aceasta trebuie să fie o listă de nume de host. Aceste nume de host specifică serverele de mail care gestionează e-mailurile pentru domeniul tău.
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
- **Înregistrare TXT**: Aceasta poate fi fie un singur șir de caractere, fie o listă de șiruri. Înregistrările TXT sunt adesea utilizate în diverse scopuri, cum ar fi verificarea proprietății domeniului și asigurarea securității e-mailurilor.
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
- **Înregistrare NS**: Aceasta trebuie să fie o listă de nume de host. Aceste nume de host specifică serverele de nume pentru domeniul tău.
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
Notă: Vă rugăm să consultați [întrebările frecvente](https://docs.is-a.dev/faq/) pentru clarificări despre ce sau cui îi permitem înregistrări NS. Dacă doriți un exemplu despre ce căutăm ca justificare, puteți [verifica acest PR](https://github.com/is-a-dev/register/pull/16758).

- **Înregistrare SRV**: Aceasta trebuie să fie o listă de înregistrări de servicii. Fiecare înregistrare specifică prioritatea, ponderea, portul și ținta pentru un serviciu de pe domeniul tău. Înregistrările SRV sunt adesea utilizate pentru servicii precum VoIP, mesagerie și altele.
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
- **Înregistrare CAA**: Aceasta trebuie să fie o listă de înregistrări de Autorizare a Autorității de Certificare (CAA). Fiecare înregistrare specifică autoritatea permisă să emită certificate SSL pentru domeniul tău, cu câmpurile pentru `flags`, `tag` și `value`.
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
- **Înregistrare DS**: Aceasta trebuie să fie o listă de înregistrări Delegation Signer (DS). Fiecare înregistrare verifică autenticitatea zonei (subdomeniului) cu câmpurile `key_tag`, `algorithm`, `digest_type` și `digest`.
```json
"DS": [{
      "key_tag": 2371,
      "algorithm": 13,
      "digest_type": 2,
      "digest": "C2074462471B81206F792AEC23469EF33DDC53538E8580DCCC92FD130C9A6096"
    }]
```

### proxied (*opțional*)
Activează proxy-ul Cloudflare pentru domeniul tău. Dezactivat implicit. Pentru a-l activa, adaugă această linie de cod:
```json
"proxied": true
```

### redirect_config (*opțional*)
- Permite puncte finale de redirecționare personalizate pentru domeniul tău. Un exemplu poate fi găsit [aici](https://github.com/is-a-dev/register/blob/main/domains/william.json).
```json
"redirect_config": {
    "custom_paths": {
      "/github": "https://github.com/wdhdev"
    },
    "redirect_paths": true
}
```
