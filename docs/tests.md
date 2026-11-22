# Tests

L'application est testée avec [Vitest](https://vitest.dev/). Les tests se trouvent dans le dossier `test/` du dépôt [roadsplanner](https://github.com/RoadsPlanner/roadsplanner).

## Deux types de tests

| Type | Dossier | Ce qui est testé | Base de données |
| --- | --- | --- | --- |
| Unitaires | `test/unit/` | les fonctions du code, une par une | non |
| Intégration | `test/integration/` | l'API complète, avec de vraies requêtes HTTP | oui (PostgreSQL) |

Au total, **30 tests**.

## Tests unitaires

Ils vérifient les fonctions de `src/lib` (code partagé entre le navigateur et le serveur) et de `src/server` (API).

| Fichier | Ce qui est vérifié |
| --- | --- |
| `dates.test.ts` | dates valides, calcul de la date de départ, chevauchement de deux étapes, tri des étapes |
| `format.test.ts` | affichage des dates en français (« 1er juil. », « Du 1er au 14 juil. 2026 »), pluriels, nom affiché |
| `phone.test.ts` | conversion d'un numéro au format international, validation, affichage |
| `roles.test.ts` | qui peut modifier et qui peut partager un roadtrip |
| `stats.test.ts` | statut d'un roadtrip (brouillon, à venir, en cours, terminé), étapes à compléter, statistiques |
| `validation.test.ts` | contrôle des données reçues par l'API (inscription, roadtrip, étape, hébergement) |
| `security.test.ts` | hachage des mots de passe, lecture du cookie de session, identifiants invalides |

## Tests d'intégration

Le fichier `api.test.ts` envoie de vraies requêtes à l'API, branchée sur une base PostgreSQL de test. Il vérifie que :

- un utilisateur peut s'inscrire, se connecter et se déconnecter ;
- on ne peut pas créer deux comptes avec le même e-mail ;
- deux étapes d'un même roadtrip ne peuvent pas se chevaucher ;
- un lecteur peut consulter un roadtrip partagé mais pas le modifier, et une personne extérieure ne le voit pas.

## Lancer les tests

Tests unitaires seuls (aucune base nécessaire) :

```bash
npm test
```

Tous les tests, avec une base de test dédiée :

```bash
docker compose exec db createdb -U roadsplanner roadsplanner_test
TEST_DATABASE_URL=postgres://roadsplanner:roadsplanner@localhost:5432/roadsplanner_test npm test
```

!!! warning "Base de test"
    La base indiquée dans `TEST_DATABASE_URL` est vidée à chaque lancement. Il ne faut jamais utiliser la base de développement.

Sans `TEST_DATABASE_URL`, les tests d'intégration sont simplement ignorés.

Pour relancer les tests automatiquement à chaque modification :

```bash
npm run test:watch
```
