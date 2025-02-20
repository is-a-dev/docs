---
icon: question
label: FAQ
route: /faq
tags: useful
---

# Foire Aux Questions (FAQ)

## Quels types d'enregistrements sont pris en charge ?

- A  
- AAAA  
- CAA  
- CNAME  
- DS  
    - **Remarque :** Ces enregistrements ne peuvent être utilisés qu'en combinaison avec des enregistrements NS, qui sont utilisés pour DNSSEC.  
- MX  
- NS  
    - **Remarque :** Ces enregistrements ne sont attribués que dans des cas spécifiques. Consultez [`Qui peut utiliser les enregistrements NS ?`](#qui-peut-utiliser-les-enregistrements-ns) pour plus d'informations.  
- SRV  
- TXT  
- URL  
    - **Remarque :** Ces enregistrements utilisent Cloudflare pour la redirection, ce n'est pas un véritable type d'enregistrement DNS.  

## Pourquoi mon domaine redirige-t-il toujours vers le site is-a.dev ?
Cela est généralement dû à la mise en cache de votre navigateur. [Vider le cache de votre navigateur](https://support.google.com/accounts/answer/32050) devrait résoudre le problème.  

## Puis-je utiliser un enregistrement CNAME avec d'autres enregistrements ?
Vous ne pouvez pas demander un sous-domaine ni soumettre des modifications contenant un enregistrement CNAME avec d'autres enregistrements (A, AAAA, MX, TXT, etc...).  

## Combien de temps faut-il pour que ma PR soit fusionnée ?
Cela dépend. Nous essayons de traiter les PRs aussi rapidement que possible, mais les mainteneurs ne peuvent pas être en ligne en permanence. Nous avons des études et du travail, ce projet est seulement une activité secondaire. Soyez patient, nous y arriverons dès que possible !  
Pour augmenter vos chances d'obtenir une révision plus rapide, postez votre PR dans [#pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) sur notre [serveur Discord](https://discord.gg/is-a-dev-830872854677422150).  

## Quels services prenez-vous en charge ?
Nous prenons en charge presque tous les services, mais voici les principaux services utilisés avec is-a.dev :  

- Cloudflare Pages  
- GitHub Pages  
- Netlify  
- Railway  
- Vercel  

## Puis-je créer des sous-domaines imbriqués (sous-sous-domaines) ?
Oui, c'est possible ! Il suffit de créer un fichier tel que `blog.example.json` et de suivre les mêmes instructions que pour `example.json`.  
Cependant, pour enregistrer `blog.example.is-a.dev`, vous devez déjà posséder `example.is-a.dev`.  

## Comment puis-je modifier mon domaine ?
Vous pouvez modifier le fichier JSON de votre domaine et soumettre une pull request pour effectuer la modification.  

## Comment puis-je supprimer mon domaine ?
Vous pouvez supprimer le fichier JSON de votre domaine et soumettre une pull request pour le supprimer.  

## Je rencontre une erreur SSL avec GitHub Pages, comment la corriger ?
Accédez aux paramètres GitHub Pages de votre dépôt de site web (probablement nommé `github-username.github.io`) et assurez-vous que l'option **"Enforce HTTPS"** est activée pour éviter cette erreur.  

## Puis-je devenir mainteneur / rejoindre l'équipe ?
Non, nous sélectionnons nous-mêmes les membres de notre équipe. Vous pouvez augmenter vos chances d'être choisi en aidant les autres sur nos forums d'assistance.  

## J'ai accidentellement divulgué des informations sensibles dans ma PR, comment la supprimer ?
Si votre PR **n'a pas encore été fusionnée**, vous pouvez envoyer un e-mail à [security@is-a.dev](mailto:security@is-a.dev) ou contacter [williamharrison sur Discord](https://discord.com/users/853158265466257448) en message privé.  
Si votre PR a **déjà été fusionnée**, nous ne pouvons malheureusement rien faire.  

## Puis-je utiliser mon domaine pour un serveur Minecraft ?
Oui, vous pouvez. Vous devez utiliser un enregistrement A combiné avec un enregistrement SRV.  

Consultez [cet article](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) de Namecheap pour plus d'informations.  

## Qui peut utiliser les enregistrements NS ?
Nous autorisons les enregistrements NS uniquement dans les cas suivants :  

- **Utilisation d'une zone privée** : Lorsque vous utilisez une adresse IP domestique via **un enregistrement A ou AAAA** derrière un service de proxy tel que Cloudflare. **Vous devez fournir une preuve d'utilisation pour que cette demande soit approuvée.**  
- **Services tiers nécessitant des enregistrements NS spécifiques** : Par exemple, Aternos, Wix ou Squarespace. Si vous ne pouvez pas gérer directement les enregistrements DNS sous ce domaine, vous devez fournir :  
  - Une documentation ou une preuve provenant du service tiers indiquant clairement cette exigence.  
  - Une preuve qu'aucune alternative (CNAME, A, AAAA, etc.) ne peut aboutir au même résultat.  

Nous **n'autorisons pas** les enregistrements NS pour les raisons suivantes :  

- **Par convenance** : Lorsque des alternatives comme A, AAAA ou CNAME sont suffisantes.  
- **Utilisation non opérationnelle** : Configurations esthétiques, tests ou usages non fonctionnels.  
- **Données invérifiables** : Toute configuration sans preuve claire et concrète de nécessité.  
- **Configurations trompeuses** : Tentatives d'usurpation d'identité, de fraude ou de manipulation d'utilisateurs.  
- **Risques de sécurité** : Toute configuration introduisant des vulnérabilités ou des risques pour la sécurité.  

***Nous nous réservons le droit de refuser les enregistrements NS à notre seule discrétion, quelle que soit la raison invoquée.***  

## Pourquoi êtes-vous si stricts avec les enregistrements NS ?
Nous devons être stricts, car ces enregistrements permettent à l'utilisateur final de faire pratiquement *tout ce qu'il veut* avec son sous-domaine.  

Comme vous pouvez l'imaginer, cela ouvre la porte à de nombreux abus, c'est pourquoi nous ne les attribuons pas librement.  

Si nous le pouvions, nous autoriserions les enregistrements NS pour tout le monde, mais ce n'est pas possible dans le monde réel.  

## Comment puis-je modifier mon sous-domaine is-a.dev ?
1. **Ouvrez votre fichier JSON** : Rendez-vous dans le répertoire `domains` de votre fork et ouvrez le fichier JSON correspondant à votre sous-domaine (`domains/sous-domaine.json`).  
2. **Apportez vos modifications** : Modifiez ou supprimez le fichier JSON pour refléter les changements souhaités.  
3. **Validez vos modifications** : Une fois les modifications effectuées, validez-les dans votre fork.  
4. **Poussez vos modifications** : Envoyez vos modifications vers votre dépôt forké sur GitHub.  
5. **Soumettez une pull request** : Rendez-vous sur votre dépôt forké sur GitHub et ouvrez une pull request.  
6. **Attendez la fusion de votre PR** : Une fois votre pull request soumise, attendez qu'elle soit examinée et fusionnée. Une fois fusionnée, vos modifications seront appliquées !  

**Remarque :** Surveillez votre PR en cas de demande de modifications.  
