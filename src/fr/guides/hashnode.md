---
icon: /media/hashnode.svg
label: Hashnode
tags: guides
---

# Blog Hashnode

Quand vous créez votre blog Hashnode, Hashnode vous fournit un sous-domaine gratuit `hashnode.dev` pour vous. Cependant, vous pouvez configurer votre propre sous-domaine `is-a.dev`.

Dans cette guide, vous apprendrez à accomplir cela.

---

1. Connectez vous à votre compte Hashnode.

2. Cliquez sur votre **avatar** en bas à gauche de la page sur **ordinateur** ou en haut à droite sur **mobile**.
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614932849541/cBNDGKXMj.png?auto=compress)

3. Cliquez sur l'option **Blog Dashboard** dans le popup modal pour accéder à votre tableau de bord de blog.
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937218081/InvxVHXDy.png?auto=compress)

4. Naviguez ensuite vers l'onglet **Domains** et entrez votre domaine sans le préfixe **www** ou **https://** dans le champ de texte fourni. Ensuite, cliquez sur le bouton **Update** pour continuer.
   ![Hashnode's Blog Domain Tab](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937377176/0cwddAywO.png?auto=compress)

5. Allez dans votre fork du dépôt `is-a-dev/register`, éditez le fichier JSON de votre sous-domaine, assurez-vous de supprimer tous les anciens enregistrements, puis ajoutez ce qui suit à la clé `record` et créez une PR:

```json
"CNAME": "hashnode.network"
```

## Configuration

Quand ce sera fini, votre blog Hashnode devrait être configuré pour utiliser votre sous-domaine. Ces changements peuvent prendre de 1 heure à environ 48 heures, donc veuillez patienter. Il sera probablement prêt dans moins d'une heure.

Quand les DNS auront été propagés, vous pourrez commencer à profiter de votre blog Hashnode avec votre sous-domaine `.is-a.dev`!

## Encore besoin d'aide ?

Si vous rencontrez des problèmes ou avez besoin d'aide supplémentaire, considérez les ressources suivantes :

- [Hashnode Domain Mapping Guide](https://support.hashnode.com/docs/mapping-domain/): Cet articles de support fournit des instructions détaillées sur comment lier votre domaine à Hashnode.
- [Hashnode Support Center](https://support.hashnode.com/): Pour une aide plus générale liée à Hashnode, visiter leur Centre D'Assistance.

Veuillez noter que is-a.dev n'est pas affilié avec Hashnode. Si vous rencontrez des problèmes avec votre blog Hashnode, veuillez demander de l'aide auprès de leurs canaux de support. Nous ne pouvons pas vous aider avec des problèmes spécifiques à Hashnode.