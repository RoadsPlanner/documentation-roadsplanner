# RGPD

Le projet en est encore à ses débuts, cette page reprend donc les points principaux du RGPD (Règlement Général sur la Protection des Données) à prendre en compte pour RoadsPlanner. Chaque point renvoie au texte officiel ou aux recommandations de la CNIL. Elle sera complétée au fur et à mesure du développement.

Les numéros d'articles renvoient au [RGPD](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32016R0679) (règlement UE 2016/679), sauf mention contraire. La liste complète des sources est en [bas de page](#sources).

## Les données concernées

Une application de road trip manipule des données personnelles, c'est-à-dire des informations qui permettent d'identifier une personne directement ou indirectement (article 4) :

- **Le compte :** nom, adresse e-mail, mot de passe.
- **Les voyages :** itinéraires, dates, lieux visités, budget.
- **Les réservations :** noms des voyageurs, numéros de réservation, adresses des hébergements.
- **La localisation :** les étapes d'un voyage permettent de savoir où se trouve une personne et à quel moment. Si on utilise le GPS du téléphone, c'est encore plus précis.
- **Les notes libres :** commentaires sur les lieux, motifs des repérages.
- **Les personnes invitées :** participants et proches avec qui le voyage est partagé, qui ne sont pas forcément inscrits.
- **Les données techniques :** adresse IP, journaux de connexion, données stockées dans le navigateur.

## Les points importants

### Base légale

Chaque traitement doit reposer sur une base légale (article 6). Pour RoadsPlanner :

- **Exécution du contrat :** le compte, les voyages et la synchronisation, puisque c'est le service demandé par l'utilisateur.
- **Consentement :** la géolocalisation, les notifications et tout ce qui n'est pas indispensable au service.

*Référence : article 6 du RGPD, [CNIL : les bases légales](https://www.cnil.fr/fr/les-bases-legales).*

### Minimisation des données

On ne collecte que ce qui est vraiment utile au fonctionnement de l'application. Par exemple, pas besoin de demander l'âge, l'adresse ou le numéro de téléphone pour planifier un voyage.

*Référence : article 5.1.c du RGPD, fiche « Minimiser les données » du [guide RGPD de l'équipe de développement](https://lincnil.github.io/Guide-RGPD-du-developpeur/).*

### Protection dès la conception

La protection des données doit être prise en compte dès le début du projet, et les réglages par défaut doivent être les plus protecteurs. Par exemple, un voyage doit être privé par défaut, et c'est l'utilisateur qui choisit de le partager.

*Référence : article 25 du RGPD.*

### Information et consentement

L'utilisateur doit savoir quelles données sont collectées, pourquoi, combien de temps elles sont gardées et à qui elles sont transmises. Il faudra donc une politique de confidentialité claire. Quand on demande un consentement, il doit être libre, explicite, et aussi facile à retirer qu'à donner.

*Référence : articles 7, 12 et 13 du RGPD, [CNIL : exemples de mentions d'information](https://www.cnil.fr/fr/rgpd-exemples-de-mentions-dinformation).*

### Les droits des utilisateurs

Chaque utilisateur doit pouvoir :

- consulter les données qu'on a sur lui (droit d'accès) ;
- les modifier ou les corriger (droit de rectification) ;
- les supprimer, en supprimant son compte (droit à l'effacement) ;
- les récupérer dans un format réutilisable, par exemple un export de ses voyages (droit à la portabilité) ;
- s'opposer à certains traitements.

La réponse doit être donnée dans un délai d'un mois.

*Référence : articles 12 et 15 à 21 du RGPD, [CNIL : les droits pour maîtriser vos données personnelles](https://www.cnil.fr/fr/les-droits-pour-maitriser-vos-donnees-personnelles).*

### La géolocalisation

La CNIL considère la localisation comme une donnée particulièrement intrusive, car elle révèle les déplacements et les habitudes d'une personne. Pour RoadsPlanner :

- la localisation du téléphone n'est demandée que quand l'utilisateur en a besoin, et jamais en arrière-plan sans raison ;
- l'utilisateur doit pouvoir s'en passer et saisir ses étapes à la main ;
- les positions ne doivent pas être transmises à des tiers.

*Référence : [CNIL : géolocalisation et applications mobiles](https://www.cnil.fr/fr/geolocalisation-applications-mobiles-proteger-vos-donnees), [CNIL : recommandations pour les applications mobiles](https://www.cnil.fr/fr/recommandations-applications-mobiles).*

### Les données sensibles

Certaines données sont dites sensibles : santé, religion, opinions politiques, orientation sexuelle, etc. Leur traitement est en principe interdit, sauf exceptions comme le consentement explicite. RoadsPlanner n'a pas besoin d'en collecter, mais les notes libres peuvent en contenir sans qu'on le veuille (par exemple une note sur un handicap pour choisir un hébergement accessible, ou un lieu de culte). Il ne faut donc pas exploiter le contenu des notes, et il faut prévenir l'utilisateur de ne pas y mettre d'informations sensibles.

*Référence : article 9 du RGPD, [CNIL : définition d'une donnée sensible](https://www.cnil.fr/fr/definition/donnee-sensible).*

### Les mineurs

Un voyage en famille peut contenir des informations sur des enfants (Nourdine voyage avec ses 4 enfants). En France, un mineur de moins de 15 ans ne peut pas consentir seul à un traitement basé sur le consentement : il faut aussi l'accord d'un parent. Pour l'instant, on part du principe que le compte est réservé aux personnes de 15 ans et plus.

*Référence : article 8 du RGPD, article 45 de la [loi Informatique et Libertés](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000886460), [CNIL : consentement d'un parent pour les mineurs de moins de 15 ans](https://www.cnil.fr/fr/recommandation-4-rechercher-le-consentement-dun-parent-pour-les-mineurs-de-moins-de-15-ans).*

### Le partage des voyages

Un voyage partagé contient aussi des informations sur les autres participants. Seules les personnes invitées doivent pouvoir y accéder, et le propriétaire du voyage doit pouvoir retirer un accès à tout moment. Les liens de partage ne doivent pas être devinables. Les personnes ajoutées qui n'ont pas de compte doivent aussi être informées que leurs données sont utilisées.

*Référence : articles 14 et 32 du RGPD.*

### Durée de conservation

Les données ne doivent pas être gardées indéfiniment. Il faudra définir une durée pour chaque type de données. Par exemple, supprimer les comptes inactifs depuis un certain temps après avoir prévenu l'utilisateur, et supprimer tout de suite les données d'un compte quand il est fermé.

*Référence : article 5.1.e du RGPD, [CNIL : les durées de conservation des données](https://www.cnil.fr/fr/les-durees-de-conservation-des-donnees).*

### Sécurité

- Les mots de passe sont stockés hachés avec un algorithme adapté, jamais en clair, et doivent respecter une robustesse minimale.
- Les échanges entre l'application et le serveur passent en HTTPS.
- L'accès à la base de données est limité aux personnes qui en ont besoin.
- Les données de test ne doivent pas être de vraies données d'utilisateurs.

*Référence : article 32 du RGPD, [CNIL : recommandation relative aux mots de passe (délibération 2022-100)](https://www.cnil.fr/sites/cnil/files/atoms/files/deliberation-2022-100-du-21-juillet-2022_recommandation-aux-mots-de-passe.pdf), [CNIL : guide de la sécurité des données personnelles](https://www.cnil.fr/fr/guide-de-la-securite-des-donnees-personnelles).*

### Les données hors ligne et le stockage dans le navigateur

Comme c'est une PWA, une partie des données est enregistrée dans le navigateur du téléphone ou de l'ordinateur pour fonctionner sans réseau. Ces données doivent être effacées quand l'utilisateur se déconnecte, surtout s'il utilise un appareil partagé.

Les règles sur les cookies s'appliquent aussi au stockage local du navigateur. Ce qui est strictement nécessaire au fonctionnement (session, données hors ligne) ne demande pas de consentement. En revanche, des outils de statistiques ou de publicité en demanderaient un.

*Référence : article 82 de la [loi Informatique et Libertés](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000886460), [CNIL : lignes directrices et recommandation sur les cookies et autres traceurs](https://www.cnil.fr/fr/cookies-et-autres-traceurs/regles/cookies/lignes-directrices-modificatives-et-recommandation).*

### Les services externes et l'hébergement

L'application va sûrement utiliser des services externes : hébergeur, service de cartes, éventuellement un service de musique. Ce sont des sous-traitants, il faut donc un contrat qui encadre ce qu'ils font des données. Si un service transfère les données hors de l'Union européenne (par exemple vers les États-Unis), ce transfert doit être encadré. Pour limiter ce problème, on privilégie un hébergement en Union européenne.

*Référence : articles 28 et 44 à 49 du RGPD, [CNIL : transférer des données hors de l'UE](https://www.cnil.fr/fr/transferer-des-donnees-hors-de-lue).*

### Violation de données

En cas de fuite ou de piratage, il faut prévenir la CNIL au plus tard 72 heures après en avoir eu connaissance, si la fuite présente un risque pour les personnes. Si le risque est élevé, il faut aussi prévenir les utilisateurs concernés. Toute violation doit être notée en interne, même si elle n'est pas notifiée.

*Référence : articles 33 et 34 du RGPD, [CNIL : notifier une violation de données personnelles](https://www.cnil.fr/fr/notifier-une-violation-de-donnees-personnelles).*

## À faire plus tard

- Rédiger la politique de confidentialité et les mentions légales.
- Tenir un registre des traitements de données (article 30, [CNIL : le registre des activités de traitement](https://www.cnil.fr/fr/RGPD-le-registre-des-activites-de-traitement)).
- Définir précisément les durées de conservation.
- Choisir l'hébergeur et lister les services externes utilisés.
- Vérifier si une analyse d'impact (AIPD) est nécessaire à cause des données de localisation (article 35, [CNIL : ce qu'il faut savoir sur l'AIPD](https://www.cnil.fr/fr/ce-quil-faut-savoir-sur-lanalyse-dimpact-relative-la-protection-des-donnees-aipd)).
- Prévoir une procédure en cas de violation de données.

## Sources

**Textes officiels**

- [Règlement (UE) 2016/679 du 27 avril 2016 (RGPD)](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32016R0679), EUR-Lex
- [Loi n° 78-17 du 6 janvier 1978 relative à l'informatique, aux fichiers et aux libertés](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000886460), Légifrance

**CNIL**

- [Guide RGPD de l'équipe de développement](https://lincnil.github.io/Guide-RGPD-du-developpeur/) ([présentation de la nouvelle version](https://www.cnil.fr/fr/la-cnil-publie-une-nouvelle-version-de-son-guide-rgpd-pour-lequipe-de-developpement))
- [Les bases légales](https://www.cnil.fr/fr/les-bases-legales)
- [Exemples de mentions d'information](https://www.cnil.fr/fr/rgpd-exemples-de-mentions-dinformation)
- [Les droits pour maîtriser vos données personnelles](https://www.cnil.fr/fr/les-droits-pour-maitriser-vos-donnees-personnelles)
- [Géolocalisation et applications mobiles](https://www.cnil.fr/fr/geolocalisation-applications-mobiles-proteger-vos-donnees)
- [Recommandations pour les applications mobiles](https://www.cnil.fr/fr/recommandations-applications-mobiles)
- [Définition d'une donnée sensible](https://www.cnil.fr/fr/definition/donnee-sensible)
- [Consentement d'un parent pour les mineurs de moins de 15 ans](https://www.cnil.fr/fr/recommandation-4-rechercher-le-consentement-dun-parent-pour-les-mineurs-de-moins-de-15-ans)
- [Les durées de conservation des données](https://www.cnil.fr/fr/les-durees-de-conservation-des-donnees)
- [Délibération n° 2022-100 du 21 juillet 2022 : recommandation relative aux mots de passe](https://www.cnil.fr/sites/cnil/files/atoms/files/deliberation-2022-100-du-21-juillet-2022_recommandation-aux-mots-de-passe.pdf)
- [Guide de la sécurité des données personnelles](https://www.cnil.fr/fr/guide-de-la-securite-des-donnees-personnelles)
- [Cookies et autres traceurs : lignes directrices et recommandation](https://www.cnil.fr/fr/cookies-et-autres-traceurs/regles/cookies/lignes-directrices-modificatives-et-recommandation)
- [Transférer des données hors de l'UE](https://www.cnil.fr/fr/transferer-des-donnees-hors-de-lue)
- [Notifier une violation de données personnelles](https://www.cnil.fr/fr/notifier-une-violation-de-donnees-personnelles)
- [Le registre des activités de traitement](https://www.cnil.fr/fr/RGPD-le-registre-des-activites-de-traitement)
- [Ce qu'il faut savoir sur l'analyse d'impact (AIPD)](https://www.cnil.fr/fr/ce-quil-faut-savoir-sur-lanalyse-dimpact-relative-la-protection-des-donnees-aipd)
