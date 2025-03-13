---
icon: /media/discord.svg
label: Discord Domain Connection
tags: guides
---

# Configurarea conexiunii de domeniu Discord cu domeniul tău is-a.dev

## Obține șirul de verificare

1. Deschide aplicația Discord și apasă pe `Settings` (Setări).
   ![](../../media/discord/step_1.png)

2. Deschide secțiunea `Connections` (Conexiuni).
   ![](../../media/discord/step_2.png)

3. Apasă butonul `View more` (Vezi mai mult).
   ![](../../media/discord/step_3.png)

4. Click pe butonul de domeniu (iconița glob).
   ![](../../media/discord/step_4.png)

5. În câmpul care apare, introdu numele tău de domeniu is-a.dev (ex: `example.is-a.dev`).
   ![](../../media/discord/step_5.png)

6. Copiază șirul de verificare.
   ![](../../media/discord/step_6.png)

### Crearea fișierului pentru domeniu

Creează un fișier JSON în folderul `domains/` numit `domains/_discord.example.json` cu următorul conținut:

```json
{
    "owner": {
        "username": "github-username",
        "email": "email@address"
    },
    "record": {
        "TXT": "discord-verification-string"
    }
}
```

## Configurare

După ce pull request-ul este acceptat, repetați pașii pentru a obține șirul de verificare și apăsați butonul `Verify` (Verifică).
Dacă apare vreo eroare precum `Unable to verify your domain` (Verificarea domainului a eșuat ), așteptați câteva minute (uneori până la 24 de ore) deoarece DNS-ul s-ar putea să nu fie încă actualizat.