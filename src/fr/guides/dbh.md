---
label: DanBot Hosting
tags: guides
icon: /media/dbh.png
---

# Utiliser DanBot Hosting avec un sous-domaine is-a.dev

Ce guide va vous guider tout au long du processus de configuration d'un site DanBot Hosting et de redirection de votre sous-domaine is-a.dev vers celui-ci.

## Obtention de l'IP du proxy

Exécutez la commande suivante dans le salon #commands du serveur Discord de [DanBot Hosting](https://discord.gg/dbh) :

```
dbh!server proxy
```

Vous aurez une réponse comme celle-ci :

![](../../media/dbh_proxy/1.jpg)

Si vous êtes sur le plan gratuit, choisissez n'importe quel proxy US. Si vous êtes un donateur, vous pouvez utiliser le proxy spécifique aux donateurs, alors notez l'adresse IP du proxy que vous avez choisi.

### Création du fichier du domaine

Créez un fichier JSON dans le dossier `domains` (`domains/subdomain.json`) avec le contenu suivant et soumettez une pull request :

```json
{
    "description": "Description de l'utilisation de ce sous-domaine",
    "repo": "https://github.com/votre-nom-d-utilisateur/votre-depot",
    "owner": {
        "username": "votre-nom-d-utilisateur",
        "email": "moi@example.com"
    },
    "records": {
        "A": ["ip-du-proxy-ici"]
    }
}
```

Note : Dans la section propriétaire, vous pouvez ajouter tout compte de réseau social, comme Discord. Si vous ajoutez un autre compte de réseau social, le champ email devient facultatif. Le nom d'utilisateur GitHub reste cependant obligatoire. N'oubliez pas d'inclure une prévisualisation de votre site dans votre pull request.

## Configuration

Après la fusion de la pull request, obtenez votre ID de serveur en exécutant cette commande :

```
dbh!server list
```

Vous aurez une réponse comme celle-ci :

![](../../media/dbh_proxy/2.jpg)

Notez l'ID de votre serveur, puis exécutez la commande suivante :

```
dbh!server proxy your-subdomain.is-a.dev yourserverid
```