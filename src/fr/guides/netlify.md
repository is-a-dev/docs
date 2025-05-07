---
icon: /media/netlify.svg
label: Netlify
tags: guides
---


# Configurer Netlify avec un sous-domaine is-a.dev

Ce guide vous guidera pour créer un déploiement Netlify et y relier votre sous-domaine is-a.dev.

## Créer un site Netlify

Premièrement, vous devez créer un site sur Netlify. Suivez les instructions sur [Netlify Docs (En anglais)](https://docs.netlify.com/).

### Créer le fichier du domaine

Dans le dossier `domains`, créez un nouveau fichier JSON pour votre sous-domaine (`domains/sous-domaine.json`) et soumettez un pull request. Ce fichier doit contenir le JSON suivant :

```json
{
    "owner": {
        "username": "nom-d'utilisateur-github",
        "email": "votre-email@example.fr"
    },
    "records": {
        "A": ["75.2.60.5"]
    }
}
```

**Note :** Dans la section *owner*, vous pouvez ajouter n'importe quel moyen de contact comme un nom d'utilisateur Discord. Si vous ajoutez un autre moyen de contact, vous pouvez omettre le champ email. Cependant, **le nom d'utilisateur GitHub est requis.** N'oubliez pas de fournir un aperçu de votre site dans votre pull request.

## Configurer Netlify
 
- Après que la pull request soit fusionnée, vous devez configurer votre site Netlify pour utiliser votre sous-domaine. Allez sur le tableau de bord de votre site Netlify.
- Naviguez vers **Site Settings > Domain Management > Custom Domains** et ajoutez `votre-domaine.is-a.dev` dans le champ donné.
- Netlify demandera une étape de vérification, nécessitant généralement d'ajouter un enregistrement DNS. Cette étape peut être ignorée si votre sous-domaine pointe déjà vers l'adresse IP de Netlify (`75.2.60.5`).

### Dernières étapes

- Attendez que le DNS se propage. Cela prend généralement quelques minutes (jusqu'à 24h).
- Votre site Netlify devrait être accessible à l'adresse `votre-domaine.is-a.dev`.
