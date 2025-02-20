---
icon: /media/vercel.svg
label: Vercel
tags: guides
---

# Mise en place avec un sous-domaine is-a.dev

Ce guide vous guidera tout au long du processus de mise en place d'un site Vercel pour pointer votre sous-domaine is-a.dev vers ce dernier.

## Vérifiez que vous avez un site Vercel

If you haven't made a Vercel site, make sure to make one. Follow the instructions in [Vercel's Docs](https://vercel.com/docs/getting-started-with-vercel).
Si vous n'avez pas fait de site Vercel, assurez-vous de le faire. Suivez les instructions dans la [documentation Vercel](https://vercel.com/docs/getting-started-with-vercel).

### Création du fichier de domaine

En premier lieu, allez dans votre tableau de bord Vercel, puis allez dans votre projet, puis allez dans Custom Domains et mettez-y le sous-domaine is-a.dev que vous voulez.

**Vous aurez besoin de faire deux fichiers pour que ce processus se déroule correctement**. Nous allons passer dans l'ordre pour cette section.

1. Créez un fichier pour la vérification TXT Vercel
   Quand vous connectez le domaine, vous serez accueilli avec une chaîne de vérification TXT. Pour faire le fichier pour ce dernier, le TXT record doit être placé dans `_vercel.sous-domaine.json` dans le **répertoire des domaines** (remplacez sous-domaine par le domaine que vous voulez) et le fichier devrait être comme ceci:
!!!
Vous pouvez également remplacer l'e-mail par n'importe quelle forme de réseau social (comme Discord, Twitter, Bluesky, Mastodon etc.).
!!!

```json
{
    "owner": {
        "username": "nom-d-utilisateur-github",
        "email": "email@exemple.com"
    },
    "record": {
        "TXT": "insérer-la-chaine-de-vérification-ici"
    }
}
```

!!!
**_NE PAS FAIRE DE PULL REQUEST MAITENANT_**, nous avons encore un autre fichier à faire. Si vous aviez fait une pull request à ce stade, nous rejetterions votre domaine car vous essayez de faire un sous-domaine imbriqué sur un sous-domaine que vous ne possédez pas encore. Veuillez passer à l'étape suivante.
!!!

1. Créez un fichier pour le domaine principal
   Maintenant, vous devez faire un fichier pour le domaine principal, nous avons deux façons de le faire : des enregistrements CNAME et A. Nous allons avoir deux différents fichiers pour ceux-là et expliquer ce que vous devez faire.

Créez `sous-domaine.json` dans le **répertoire des domaines** (remplacez sous-domaine par le domaine que vous avez choisi) et mettez-y l'un de ces types :

**Enregistrement CNAME**: Si vous utilisez un enregistrement CNAME, vous n'avez pas besoin de fournir une prévisualisation, car vous utilisez le site comme le CNAME, mais vous ne pouvez pas utiliser d'autre enregistrement (comme des enregistrements MX et TXT). **Cette option est idéale pour ceux qui ne veulent que leur domaine pour leur site**.

```json
{
    "owner": {
        "username": "nom-d-utilisateur-github",
        "email": "email@exemple.com"
    },
    "record": {
        "CNAME": "nom-de-domaine.vercel.app"
    }
}
```

**Enregistrement A**: Si vous utilisez un enregistrement A, vous devrez fournir une prévisualisation soit en plaçant un lien dans la section de commentaire de la PR, en le plaçant dans la description, soit en fournissant une capture d'écran de votre site web. **Cette option est idéale pour ceux qui veulent utiliser leur domaine pour leur site et leur email**.

```json
{
    "owner": {
        "username": "nom-d-utilisateur-github",
        "email": "email@exemple.com"
    },
    "record": {
        "A": ["76.76.21.21"]
    }
}
```

### Création de votre pull request

Quand vous aurez fait ces deux fichiers, vous pourrez faire une pull request dans le [dépôt principal](https://github.com/is-a-dev/register), puis vous devrez patienter jusqu'à qu'elle soit fusionnée. Si vous voulez une change que votre PR soit fusionnée plus rapidement, rejoignez notre [serveur Discord](https://discord.gg/is-a-dev-830872854677422150).

Quand votre PR aura été fusionnée, votre site devrait fonctionner. Si ce n'est pas le cas, effacez votre cache.