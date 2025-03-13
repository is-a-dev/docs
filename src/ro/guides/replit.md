---
icon: /media/replit.svg
label: Replit
tags: guides
---

# Configurarea Replit cu subdomeniul tău is-a.dev

## Crearea unui proiect

Urmează instrucțiunile din [Ghidul Replit](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) pentru a crea un proiect.

### Conectează repl-ul tău la subdomeniul is-a.dev

Urmează instrucțiunile din [Ghidul Domeniilor Personalizate Replit](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl).

Urmează doar secțiunea "Connecting your domain to your repl", apoi revino la acest ghid pentru pașii următori.

### Crearea fișierului pentru domeniu

Creează un fișier JSON în folderul `domains` (`domains/subdomain.json`) cu următorul conținut:

**Notă:** Nu adăuga niciun record TXT, chiar dacă Replit îți cere să faci asta.

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "CNAME": "siteid.id.repl.co"
    }
}
```
## Finalizare

Odată ce pull request-ul tău a fost aprobat și îmbinat, ar trebui să poți accesa noul tău subdomeniu is-a.dev conectat la site-ul tău Replit!
