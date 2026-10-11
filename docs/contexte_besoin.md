# Contexte et besoins du projet

## Le constat

Préparer un road trip demande de rassembler beaucoup d'informations : l'itinéraire, les lieux à visiter, les réservations, le budget, le matériel à emporter, la musique pour la route... Aujourd'hui, ces informations sont souvent éparpillées entre plusieurs applications : Google Maps pour les lieux, un agenda pour les dates, un tableur pour le budget, Instagram pour les repérages, Spotify pour la musique.

Ce fonctionnement pose plusieurs problèmes :

- **Dispersion :** une même information se retrouve dans plusieurs applications, et un point sur une carte ne veut plus rien dire quelques semaines après si on n'a pas noté pourquoi on l'avait ajouté.
- **Réseau :** sur la route, la connexion n'est pas toujours là. Une application qui ne fonctionne hors ligne « que si on y a pensé avant » ne sert à rien au moment où on en a besoin.
- **Synchronisation :** on prépare souvent sur ordinateur, mais on consulte sur téléphone. Si les deux ne sont pas synchronisés, on perd du temps, voire des données.
- **Partage :** quand on voyage à plusieurs, chacun a souvent sa propre version du planning, et les proches qui veulent suivre le voyage doivent installer une application de plus.

## Application concrète

De ces constats est née l'idée de **RoadsPlanner** : une seule application qui regroupe toute la préparation d'un road trip, utilisable aussi bien sur ordinateur que sur téléphone, et qui continue de fonctionner sans réseau.

Pour bien cerner les attentes, nous avons commencé par définir des [personas](personas.md) représentant nos futurs utilisateurs, puis nous avons comparé les approches techniques possibles dans un [tableau comparatif](comparatif.md).

## Cibles et contraintes

L'application est destinée à différents types de voyageurs, qui apportent chacun leur lot de contraintes :

- Les organisateurs : ils préparent tout dans le détail sur grand écran, et veulent pouvoir adapter le programme sur téléphone en cas d'imprévu. Pour eux, la fiabilité de la sauvegarde et de la synchronisation entre le PC et le téléphone est indispensable. Ils ont aussi besoin d'outils d'organisation comme la gestion du budget et la liste de matériel.

- Les voyageurs à deux ou en groupe : ils veulent un planning commun, partagé en temps réel, plutôt que chacun le sien. L'application doit rester simple et le hors ligne doit être activé par défaut, sans configuration.

- Les voyageurs légers : ils partent avec peu de matériel, parfois avec un téléphone ancien dont la mémoire est presque pleine. L'application doit donc être légère, ne pas obliger à passer par un magasin d'applications, et permettre d'envoyer l'itinéraire à quelqu'un sans qu'il ait à télécharger quoi que ce soit. Ils tiennent aussi à garder la main sur leurs données.

- Les proches : les personnes extérieures au voyage (par exemple les grands-parents) qui veulent suivre ou participer. Pour eux, l'accès doit être le plus simple possible, idéalement un simple lien.

## Besoins retenus

À partir de ces profils, nous avons retenu les besoins suivants :

| Besoin | Pourquoi |
| --- | --- |
| Planifier sur ordinateur et consulter sur téléphone | Préparer confortablement, adapter sur la route |
| Fonctionner hors ligne par défaut | Le réseau n'est pas garanti pendant un road trip |
| Synchroniser les données | Retrouver la même chose sur tous les appareils |
| Partager le voyage | Planning commun et accès pour les proches |
| Regrouper lieux, réservations et notes | Ne plus jongler entre plusieurs applications |
| Gérer le budget et le matériel | Ne rien oublier avant de partir |
| Rester léger et simple | Téléphones peu performants, pas de fonctionnalités superflues |
