---
label: ImprovMX
icon: /media/improvmx.svg
tags: guides
---

# Mise en place d'ImprovMX avec un sous-domaine is-a.dev

Ce guide vous guidera tout au long du processus d'installation d'ImprovMX avec votre sous-domaine is-a.dev.

## Ce dont vous aurez besoin avant de continuer.

1. Avoir un compte ImprovMX. Si vous n'en avez pas, veuillez aller sur [leur site](https://improvmx.com) et en créer un.
2. Vous devriez avoir déjà fait un fork du [référentiel is-a.dev](https://github.com/is-a-dev/register). Si vous ne l'avez pas fait, faites un fork en utilisant [ce lien](https://github.com/is-a-dev/register/fork).

## Création du fichier

En premier lieu, allez dans le fork que vous avez fait, puis allez dans le dossier `domains` et créez un fichier. Le fichier devrait être nommé comme ceci: `sous-domaine`. (Remplacez `sous-domaine` par le nom de sous-domaine que vous voulez.)

Après avoir créé le fichier vous devez le remplir comme suit:
```json
{
    "owner": {
        "username": "nom-d-utilisateur-github",
        "email": "moi@exemple.com"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**Après avoir fait le fichier, vous devez faire une pull request sur le [référentiel is-a.dev](https://github.com/is-a-dev/register).**s

## Configuration

Après avoir été fusionné, il devrait commencer à fonctionner automatiquement. Si vous n'avez pas configuré le domaine auparavant, veuillez aller sur le [tableau de bord ImprovMX](https://app.improvmx.com/) et ajouter le domaine.