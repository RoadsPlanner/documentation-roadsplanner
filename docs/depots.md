# Organisation des dépôts

Le projet est hébergé sur l'organisation GitHub [RoadsPlanner](https://github.com/RoadsPlanner). Elle contient pour l'instant deux dépôts, en plus de celui de cette documentation.

## roadsplanner

Dépôt principal de l'application : **PWA de planification de road trips**.

Pour l'instant, il contient la structure de base du projet :

```
roadsplanner/
├── database/   # partie base de données
└── public/     # fichiers publics de la PWA
```

Le code de l'application viendra s'ajouter au fur et à mesure du développement.

## personas-comparatif

Dépôt qui regroupe le travail de conception réalisé avant le développement :

- `personas.md` : les trois personas (Nourdine, Dulguun, Léa), détaillés sur la page [Personas](personas.md).
- `comparatif.md` : la version texte du tableau comparatif.
- `tableau-comparatif.png` : le tableau comparatif Cross-plateforme / PWA installée, présenté sur la page [Comparatif technologique](comparatif.md).

## documentation-roadsplanner

Dépôt de ce site. Il est construit avec MkDocs et le thème Material, et il est publié automatiquement sur GitHub Pages à chaque push sur la branche `main` grâce à un workflow GitHub Actions.
