---
label: Codeberg Pages
icon: /media/codeberg.svg
tags: guides
---

# Mise en place de Codeberg Pages avec le sous-domaine is-a.dev

Ce guide vous guidera tout au long du processus de mise en place d'un site Codeberg Pages pour ensuite pointer votre sous-domaine is-a.dev vers ce dernier.

## Création d'un site Codeberg Pages

En premier lieu, vous devrez créer un site sur Codeberg Pages. Suivez les instructions du [Guide Codeberg Pages](https://docs.codeberg.org/codeberg-pages/).

### Création du fichier du domaine

Créez un fichier JSON dans le dossier `domains` (domains/subdomain.json) avec le contenu suivant et soumettez une pull request :

```json
{
    "owner": {
        "username": "votre-nom-d-utilisateur-codeberg",
        "email": "votre-email"
    },
    "record": {
        "CNAME": "pages.votre-nom-d-utilisateur.codeberg.page"
    }
}
```

### Ajout du fichier `.domains`

Quand votre PR est fusionnée, créez un fichier `.domains` pour pointer votre site vers votre nouveau sous-domaine is-a.dev et ajoutez votre sous-domaine (`votre-sous-domaine.is-a.dev`) à celui-ci.

### Terminé!

Si vous avez suivi correctement la documentation tout devrait être correct et bien fonctionner :)