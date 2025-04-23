---
icon: /media/replit.svg
label: Replit
tags: guides
---

# Mise en place de Replit avec votre sous-domaine is-a.dev

## Création du projet

Suivez les instructions du [guide Replit Workspace](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) sur "Comment créer un projet".

### Connexion de votre repl à votre sous-domaine is-a.dev

Suivez les instructions du [guide Replit Custom Domains](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl).

Suivez uniquement la section "Connexion de votre domaine à votre repl" puis retournez sur ce guide pour les étapes suivantes.

### Création du fichier du domaine

Créez un fichier JSON dans le répertoire `domains` (`domains/sous-domaine.json`) avec le contenu suivant:

**Note:** N'ajoutez pas d'enregistrements TXT, même si Replit vous demande de le faire.

```json
{
    "owner": {
        "username": "nom-d-utilisateur-github",
        "email": "moi@exemple.com"
    },
    "records": {
        "CNAME": "id-de-site.id.repl.co"
    }
}
```

## Finish

Once your pull request has been merged you should be able to visit your new is-a.dev subdomain connected to your Replit site!
