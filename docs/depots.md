# Organisation des dépôts

Le projet est hébergé sur l'organisation GitHub [RoadsPlanner](https://github.com/RoadsPlanner). Voici les dépôts liés à l'application et à sa documentation.

## roadsplanner

Dépôt principal de l'application : **PWA de planification de road trips**.

L'application est construite avec Next.js, TypeScript et PostgreSQL :

```
roadsplanner/
├── app/        # pages Next.js et point d'entrée de l'API (/api)
├── src/
│   ├── lib/        # types, constantes et règles partagés navigateur / serveur
│   ├── server/     # API : contrôleurs, validation, sécurité, base de données
│   ├── components/ # composants de l'interface
│   ├── screens/    # écrans de l'application
│   └── hooks/      # logique réutilisable de l'interface
├── public/     # images et icônes de la PWA
├── test/       # tests unitaires et d'intégration
└── docs/       # stories, décisions techniques et maquettes
```

Les tests sont présentés sur la page [Tests](tests.md).

## personas-comparatif

Dépôt qui regroupe le travail de conception réalisé avant le développement :

- `personas.md` : les trois personas (Nourdine, Dulguun, Léa), détaillés sur la page [Personas](personas.md).
- `comparatif.md` : la version texte du tableau comparatif.
- `tableau-comparatif.png` : le tableau comparatif Cross-plateforme / PWA installée, présenté sur la page [Comparatif technologique](comparatif.md).

## documentation-roadsplanner

Dépôt de ce site. Il est construit avec MkDocs et le thème Material, et il est publié automatiquement sur GitHub Pages à chaque push sur la branche `main` grâce à un workflow GitHub Actions.

## guide-utilisateur-roadsplanner

Dépôt du [guide utilisateur](https://roadsplanner.github.io/guide-utilisateur-roadsplanner/), destiné aux personnes qui utilisent l'application : créer un compte, préparer un roadtrip, partager un voyage. Il est séparé de cette documentation, qui s'adresse plutôt à l'équipe et au suivi du projet.

Comme ce site, il est construit avec MkDocs et publié sur GitHub Pages à chaque push sur `main`.
