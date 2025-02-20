---
icon: file-code
label: Structure de Domaine
tags: useful
---
# Structure de Domaine
Pour enregistrer un sous-domaine, vous devez créer un nouveau fichier JSON dans le répertoire `domains` via une pull request. Par exemple, pour enregistrer `example.is-a.dev`, vous devez créer un fichier nommé `example.json` dans le répertoire `domains`. Le chemin complet serait `domains/example.json`.

## Nom du fichier

**Remarque** : Vous pouvez inclure des `.` (points) dans votre nom de fichier pour enregistrer un sous-sous-domaine (par exemple, `blog.example.is-a.dev`). Cependant, chaque segment de votre sous-domaine doit respecter les critères suivants :

Le nom de fichier :

- Doit être alphanumérique, en minuscules, avec des tirets comme séparateurs.
- Doit contenir au moins 1 caractère.
- Doit avoir une extension `.json`.

### Exemples de noms de fichiers invalides
- `.json` (le nom du fichier contient moins d’un caractère)
- `A.json` (le nom du fichier contient des lettres majuscules)
- `a..json` (le nom du fichier contient des points consécutifs)
- `.a.json` (le nom du fichier commence par un point)
- `a .json` (le nom du fichier contient un espace)
- `a$.json` (le nom du fichier contient un caractère non alphanumérique)
- `a.json.json` (le nom du fichier contient plus d’une extension `.json`)
- `a.is-a.dev.json` (le nom du fichier contient `.is-a.dev`)

### Exemples de noms de fichiers valides
Tous les noms de fichiers ci-dessous respectent les critères. La raison indiquée entre parenthèses est un exemple d’un critère qu’ils remplissent.

- `a.json` (au moins 1 caractère de long)
- `example.json` (alphanumérique et en minuscules)
- `blog.example.json` (inclut des points pour enregistrer un sous-sous-domaine)
- `my-blog.json` (utilise des tirets comme séparateurs, ce qui est recommandé)

**REMARQUE :** Afin d’empêcher une personne d’avoir un monopole sur les sous-domaines d’une seule lettre, nous limitons chacun à un seul sous-domaine d’une lettre.

### Exemple de fichier JSON
`domains/docs.json`

```json
{
  "description": "Site web de documentation pour is-a.dev",
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

### Owner (obligatoire)
Vous devez spécifier certaines informations vous concernant ici. Cela permet de vous contacter si nécessaire.
Dans l’objet owner, les champs `username` et `email` sont obligatoires. Vous pouvez ajouter plus d’informations dans cet objet si vous le souhaitez.
```json
{
  "owner": {
    "username": "github-username"
  }
}
```

### Description
Décrivez votre nom de domaine et son utilisation. Ceci est uniquement à des fins de documentation et est optionnel.

### Repo
Ceci est un lien vers le dépôt de votre site Web ou votre compte GitHub. Ceci est uniquement à des fins de documentation et est optionnel.

### Record (obligatoire)  
Cette section est l’endroit où vous spécifiez les enregistrements DNS.  

Vous pouvez voir une liste des types pris en charge [ici](./faq#which-records-are-supported).  

Vous trouverez ci-dessous quelques exemples pour les types d’enregistrements donnés :  

- **Enregistrement CNAME** : Il doit s’agir d’un nom d’hôte (`quelquechose.tld`). Il ne peut pas être utilisé en même temps que d’autres types d’enregistrements. Il est généralement utilisé pour mapper votre domaine à un serveur spécifique.  
```json
{
  "record": {
    "CNAME": "nom-utilisateur-github.github.io"
  }
}
```
- **Enregistrement A** : Il doit s’agir d’une liste d’adresses IPv4. Ces adresses pointent votre domaine vers un serveur spécifique.  
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
- **Enregistrement AAAA** : Il doit s’agir d’une liste d’adresses IPv6. Comme l’enregistrement A, ces adresses pointent votre domaine vers un serveur spécifique.  
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
- **Enregistrement URL** : Celui-ci redirige votre domaine vers une autre URL.  
```json
{
  "record": {
    "URL": "https://exemple.com"
  }
}
```
- **Enregistrement MX** : Il doit s’agir d’une liste de noms d’hôte. Ces noms d’hôte spécifient les serveurs de messagerie qui gèrent les e-mails pour votre domaine.  
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
- **Enregistrement TXT** : Il peut s’agir soit d’une seule chaîne de caractères, soit d’une liste de chaînes. Les enregistrements TXT sont souvent utilisés à diverses fins, telles que la vérification de la propriété du domaine et la sécurisation des e-mails.  
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
- **Enregistrement NS** : Il doit s’agir d’une liste de noms d’hôte. Ces noms d’hôte spécifient les serveurs DNS faisant autorité pour votre domaine.  
```json
{
  "record": {
    "NS": [
      "ns1.exemple.com",
      "ns2.exemple.com"
    ]
  }
}
```
**Remarque** : Veuillez consulter la [foire aux questions](https://docs.is-a.dev/faq/) pour des précisions sur ce que nous acceptons ou non en matière d’enregistrements NS. Si vous souhaitez voir un exemple de ce que nous attendons comme justification, vous pouvez consulter [cette PR](https://github.com/is-a-dev/register/pull/16758).  

- **Enregistrement SRV** : Il doit s’agir d’une liste d’enregistrements de service. Chaque enregistrement spécifie la priorité, le poids, le port et la cible d’un service sur votre domaine. Les enregistrements SRV sont souvent utilisés pour des services tels que la VoIP, la messagerie, et plus encore.  
```json
{
  "record": {
    "SRV": [
      {
        "priority": 10,
        "weight": 5,
        "port": 8080,
        "target": "srv.exemple.com"
      },
      {
        "priority": 20,
        "weight": 10,
        "port": 9090,
        "target": "srv2.exemple.com"
      }
    ]
  }
}
```
- **Enregistrement CAA** : Il doit s’agir d’une liste d’enregistrements d’autorisation de certification (CAA). Chaque enregistrement spécifie l’autorité autorisée à émettre des certificats SSL pour votre domaine, avec des champs pour `flags`, `tag` et `value`.  
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
- **Enregistrement DS** : Il doit s’agir d’une liste d’enregistrements de type Delegation Signer (DS). Chaque enregistrement vérifie l’authenticité de la zone (sous-domaine) avec les champs `key_tag`, `algorithm`, `digest_type` et `digest`.  
```json
"DS": [{
      "key_tag": 2371,
      "algorithm": 13,
      "digest_type": 2,
      "digest": "C2074462471B81206F792AEC23469EF33DDC53538E8580DCCC92FD130C9A6096"
    }]
```

### proxied (*optionnel*)  
Active la protection via le proxy Cloudflare pour votre domaine. Désactivé par défaut. Pour l’activer, ajoutez cette ligne de code :  
```json
"proxied": true
```
