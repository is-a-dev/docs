---
label: Other services
icon: server
tags: guides
---

# Mise en place d'autre services avec is-a.dev

## Mise en place des enregistrements DNS

Lisez la [structure des fichiers de domaine](../useful/domain-structure) et configurez les enregistrements DNS en conséquence.

## Configuration du serveur

Après que la pull request sera fusionnée, configurez votre serveur (apache, nginx, etc.) pour fonctionner avec `sous-domaine.is-a.dev`. Si vous ne savez pas comment configurer votre serveur, vous pouvez créer une issue pour un support sur le référentiel Github, ou vous pouvez aller sur le [serveur Discord](https://discord.gg/is-a-dev-830872854677422150).

Vous devriez aussi inclure `sous-domaine.is-a.dev` dans votre certificat SSL pour éviter les erreurs de certificat.