---
icon: /media/railway.png
label: Railway
tags: guides
---

# Configurer un domaine is-a.dev avec Railway

## Obtenir l'enregistrement CNAME

1. Rendez vous sur le [dashboard](https://railway.app/dashboard)
2. Allez dans le projet
3. Allez dans services.
4. Passez sur l'onglet **Settings**.
5. Cliquez sur le bouton **+ Custom Domain**.
6. Entrez le sous domaine `is-a.dev` que vous voulez utiliser.
7. Copiez le champ **Value**.
8. Pour votre domaine, créez un JSON comme celui ci-dessous:
```json
{
  "owner": {
    "username": "votre-pseudo",
    "email": "votre-email"
  },
  "records": {
    "CNAME": "la-valeur-copiée"
  }
}
```
9. Après avoir enregistré le fichier, vous devez faire une pull-request.
!!!
**Ajouter un apercu du site est obligatoire**, car la valeur CNAME donnée par Railway ne montre pas le site que vous reliez.
!!!

**Si votre PR a été fusionné, les enregistrements DNS vont s'actualiser dans quelques minutes (jusqu'a 48h).**
