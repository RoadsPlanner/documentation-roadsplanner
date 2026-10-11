# Choix de la technologie pour l'application

## Le type d'application

Le [comparatif](comparatif.md) montre que les deux approches ont chacune leurs avantages. L'application cross-plateforme est la plus puissante, mais notre projet n'a pas besoin de tout ce qu'elle apporte : RoadsPlanner sert à gérer des étapes, des lieux, des listes et un planning, pas à piloter des capteurs Bluetooth ou une montre connectée.

Nous avons donc confronté les deux solutions aux besoins de nos [personas](personas.md).

## Pourquoi une PWA

### Un seul code pour l'ordinateur et le téléphone

Nos trois personas préparent leur voyage sur ordinateur puis le consultent sur téléphone. Avec une PWA, c'est exactement le même code qui tourne sur les deux : il n'y a pas de version ordinateur à part, ni de parties à réécrire pour iPhone et pour Android.

### Pas de magasin d'applications

Léa a un téléphone presque plein et désinstalle des applications avant chaque départ. Elle veut aussi envoyer son itinéraire à une amie sans que celle-ci ait à télécharger quoi que ce soit. Nourdine, lui, veut faire participer des proches comme les grands-parents. Avec une PWA, un simple lien suffit : pas d'App Store ni de Play Store, et pas de validation à attendre à chaque nouvelle version.

### Le hors ligne

C'est le point le plus important pour nos utilisateurs. Une PWA installée garde ses données dans le navigateur, ce qui permet de consulter son voyage sans réseau. La limite est que l'envoi des données vers le serveur se fait quand on rouvre l'application, et pas en arrière-plan. Pour un road trip c'est suffisant, à condition de bien l'indiquer à l'utilisateur, par exemple avec un indicateur de synchronisation.

### Le temps de développement

Une PWA se développe avec les outils habituels du web. Il n'y a pas de nouveau langage à apprendre ni d'émulateurs à installer, ce qui nous permet d'avoir un premier écran fonctionnel rapidement et de passer plus de temps sur les fonctionnalités.

## Les limites acceptées

Le choix de la PWA a aussi des inconvénients, que nous avons jugés acceptables pour ce projet :

- Pas d'accès au Bluetooth sur iPhone : RoadsPlanner n'en a pas besoin.
- Pas de synchronisation en arrière-plan : la synchronisation se fait à l'ouverture de l'application.
- Le hors ligne n'est vraiment fiable que si l'application est installée sur l'écran d'accueil : il faudra guider l'utilisateur lors de la première utilisation.

## Conclusion

Au terme de notre analyse, la PWA s'est imposée comme la solution la plus adaptée pour RoadsPlanner. Elle répond aux besoins de nos personas (préparer sur ordinateur, consulter sur téléphone, partager par un simple lien, fonctionner hors ligne) tout en restant légère et rapide à mettre en place. Les limites de la PWA concernent surtout l'accès au matériel du téléphone, ce qui n'est pas au cœur de notre application.
