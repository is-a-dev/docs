---
icon: /media/render.svg
label: Render
tags: guides
---

# Configurer Render avec un sous-domaine is-a.dev

Ce guide vous guidera pour créer un déploiement Render et y relier votre sous-domaine is-a.dev.


## Créer un service Render

Premièrement, vous devez créer un service sur Render. Suivez les instructions sur [Render Docs (en)](https://docs.render.com/).

### Créer le fichier du domaine

Dans le dossier domains, créez un nouveau fichier JSON pour votre sous-domaine (domains/sous-domaine.json) et soumettez un pull request. Ce fichier doit contenir le JSON suivant :

```json
{
    "owner": {
          "username": "nom-d'utilisateur-github",
        "email": "votre-email@example.fr"
    },
    "records": {
        "A": ["216.24.57.1"]
    }
}
```

**Note :** Dans la section *owner*, vous pouvez ajouter n'importe quel moyen de contact comme un nom d'utilisateur Discord. Si vous ajoutez un autre moyen de contact, vous pouvez omettre le champ email. Cependant, **le nom d'utilisateur GitHub est requis.** N'oubliez pas de fournir un aperçu de votre site dans votre pull request.


## Configurer Render
 
- Après que la pull request soit fusionnée, vous devez configurer votre service Render pour utiliser votre sous-domaine. Allez sur le tableau de bord de votre service Render.
- Naviguez vers **Settings > Custom Domains** et ajoutez `votre-domaine.is-a.dev` dans le champ donné.
- Render demandera une étape de vérification, nécessitant généralement d'ajouter un enregistrement DNS. Cette étape peut être ignorée si votre sous-domaine pointe déjà vers l'adresse IP de Render (`216.24.57.1`).

### Dernières étapes

- Attendez que le DNS se propage. Cela prend généralement quelques minutes (jusqu'à 24h).
- Votre service Render devrait être accessible à l'adresse `votre-domaine.is-a.dev`.
