# RGPD

Le projet en est encore à ses débuts, cette page reprend donc les points principaux du RGPD (Règlement Général sur la Protection des Données) à prendre en compte pour RoadsPlanner. Elle sera complétée au fur et à mesure du développement.

## Les données concernées

Une application de road trip manipule des données personnelles, dont certaines sont assez sensibles :

- **Le compte :** nom, adresse e-mail, mot de passe.
- **Les voyages :** itinéraires, dates, lieux visités, réservations, budget.
- **La localisation :** les étapes d'un voyage permettent de savoir où se trouve une personne et à quel moment.
- **Le partage :** les personnes invitées sur un voyage (participants, proches).

## Les points importants

### Minimisation des données

On ne collecte que ce qui est vraiment utile au fonctionnement de l'application. Par exemple, pas besoin de demander l'âge, l'adresse ou le numéro de téléphone pour planifier un voyage.

### Consentement et information

L'utilisateur doit savoir quelles données sont collectées et pourquoi. Il faudra donc prévoir une politique de confidentialité claire, et demander son accord pour tout ce qui n'est pas indispensable (géolocalisation, notifications, cookies non essentiels).

### Les droits des utilisateurs

Chaque utilisateur doit pouvoir :

- consulter les données qu'on a sur lui ;
- les modifier ou les corriger ;
- les supprimer, en supprimant son compte ;
- les récupérer (export de ses voyages par exemple).

### Le partage des voyages

Un voyage partagé contient aussi des informations sur les autres participants. Seules les personnes invitées doivent pouvoir y accéder, et le propriétaire du voyage doit pouvoir retirer un accès à tout moment. Les liens de partage ne doivent pas être devinables.

### Durée de conservation

Les données ne doivent pas être gardées indéfiniment. Il faudra définir une durée de conservation, par exemple supprimer les comptes inactifs depuis un certain temps après avoir prévenu l'utilisateur.

### Sécurité et hébergement

- Les mots de passe sont stockés chiffrés (hachés), jamais en clair.
- Les échanges entre l'application et le serveur passent en HTTPS.
- Les données sont hébergées de préférence en Union européenne.

### Les données hors ligne

Comme c'est une PWA, une partie des données est enregistrée dans le navigateur du téléphone ou de l'ordinateur pour fonctionner sans réseau. Ces données doivent être effacées quand l'utilisateur se déconnecte, surtout s'il utilise un appareil partagé.

## À faire plus tard

- Rédiger la politique de confidentialité et les mentions légales.
- Tenir un registre des traitements de données.
- Définir précisément les durées de conservation.
- Choisir l'hébergeur.
