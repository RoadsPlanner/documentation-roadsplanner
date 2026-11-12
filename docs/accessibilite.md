# Accessibilité

L'accessibilité numérique consiste à rendre une application utilisable par tout le monde, y compris les personnes en situation de handicap : handicap visuel (aveugles, malvoyants, daltoniens), auditif, moteur (difficulté à utiliser une souris ou un écran tactile), cognitif, ou les personnes âgées dont la vue et la précision baissent. D'après l'Organisation mondiale de la santé, environ 1,3 milliard de personnes, soit une personne sur six dans le monde, vivent avec un handicap important.

Comme pour le [RGPD](rgpd.md), le projet en est à ses débuts : cette page reprend les règles qui existent, ce qui s'applique ou non à RoadsPlanner, et les bonnes pratiques qu'on veut suivre dès le début. Chaque point renvoie au texte officiel ou à la norme correspondante. La liste complète des sources est en [bas de page](#sources).

## Pourquoi c'est important pour RoadsPlanner

Plusieurs situations de nos [personas](personas.md) touchent directement à l'accessibilité :

- **Les proches :** Nourdine veut faire participer les grands-parents. Une personne âgée a souvent besoin d'un texte plus grand, de contrastes forts et de boutons faciles à toucher.
- **Le téléphone pendant le voyage :** on consulte l'application dans une voiture, en plein soleil, parfois d'une seule main. Un handicap temporaire ou une situation difficile demandent les mêmes efforts qu'un handicap permanent.
- **Les vieux téléphones :** Léa utilise un Android de 2021. Une application légère, qui supporte le zoom et les réglages de taille de texte du téléphone, reste utilisable sur un petit écran.
- **Le partage par lien :** un invité qui ouvre le voyage ne choisit pas son appareil. Il peut utiliser un lecteur d'écran, une plage braille ou une navigation au clavier.

Un voyageur en situation de handicap a aussi des besoins propres à la préparation du voyage (hébergement accessible, places de stationnement réservées, toilettes adaptées). RoadsPlanner doit lui permettre de noter ces informations facilement, en gardant en tête que ce sont des données de santé (voir la partie sur les données sensibles de la page [RGPD](rgpd.md#les-donnees-sensibles)).

## Les règles obligatoires

### En France : l'article 47 de la loi de 2005

La loi n° 2005-102 du 11 février 2005 pour l'égalité des droits et des chances des personnes handicapées impose, dans son article 47, que les services en ligne (sites, applications mobiles, logiciels) soient accessibles. L'obligation concerne :

- les personnes morales de droit public (État, collectivités, établissements publics, universités...) ;
- les organismes privés chargés d'une mission de service public, et ceux créés par des organismes publics ;
- les entreprises dont le chiffre d'affaires dépasse un seuil fixé par décret.

Les organismes concernés doivent :

- publier une **déclaration d'accessibilité** qui indique le niveau de conformité du service ;
- afficher sur la page d'accueil une **mention clairement visible** qui dit si le service est conforme ou non ;
- publier un **schéma pluriannuel** de mise en accessibilité (3 ans maximum) et des plans d'actions annuels ;
- donner un moyen de **signaler un problème** d'accessibilité.

*Référence : [article 47 de la loi n° 2005-102](https://www.legifrance.gouv.fr/loda/article_lc/LEGIARTI000048050213), [DINUM : les obligations](https://accessibilite.numerique.gouv.fr/obligations/).*

### Les sanctions

Depuis l'ordonnance du 6 septembre 2023, c'est l'Arcom qui contrôle le respect de ces obligations. Après une mise en demeure rendue publique, la sanction peut aller jusqu'à **50 000 €** si le service n'est pas accessible, et **25 000 €** si la déclaration d'accessibilité, la mention sur la page d'accueil ou le schéma pluriannuel manquent.

*Référence : [article 47-1 de la loi n° 2005-102](https://www.legifrance.gouv.fr/loda/article_lc/LEGIARTI000048050174).*

### En Europe : l'acte européen sur l'accessibilité

La directive (UE) 2019/882, appelée « European Accessibility Act », s'applique depuis le **28 juin 2025**. Elle étend l'obligation d'accessibilité à des produits et services du secteur privé : commerce en ligne, services bancaires, livres numériques, communications électroniques, et certains services de transport de voyageurs (sites, applications et billetterie). En France, elle a été transposée dans la loi de 2005 et dans le Code de la consommation.

Les **microentreprises** (moins de 10 salariés et moins de 2 millions d'euros de chiffre d'affaires ou de bilan annuel) qui fournissent des services ne sont pas concernées.

*Référence : [directive (UE) 2019/882](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32019L0882), [Conseil de l'UE : accessibilité des produits et services](https://www.consilium.europa.eu/fr/policies/accessibility-goods-services/).*

### Le référentiel à suivre : le RGAA

En France, l'accessibilité se vérifie avec le **RGAA** (Référentiel général d'amélioration de l'accessibilité), publié par la DINUM. La version en vigueur est la **4.1.2**, qui contient 106 critères (images, couleurs, formulaires, navigation, etc.). Chaque critère est accompagné de tests pour vérifier si une page le respecte. Une version 5 est en cours de rédaction, avec une publication prévue fin 2026.

Le RGAA s'appuie sur les **WCAG** (Web Content Accessibility Guidelines), les règles internationales du W3C, et reprend leurs critères de niveau A et **AA**. La dernière version, les WCAG 2.2, est une recommandation officielle du W3C depuis décembre 2024 ; c'est elle que le RGAA 5 doit intégrer.

*Référence : [RGAA 4.1.2](https://accessibilite.numerique.gouv.fr/), [critères et tests du RGAA](https://accessibilite.numerique.gouv.fr/methode/criteres-et-tests/), [WCAG 2.2](https://www.w3.org/TR/WCAG22/).*

### Et pour RoadsPlanner ?

Aujourd'hui, RoadsPlanner est un projet étudiant : ce n'est ni un service public, ni une entreprise au-dessus du seuil, ni un des services listés par la directive européenne (on ne vend rien, on ne fait pas de transport ni de réservation). L'application n'est donc **pas soumise** à ces obligations pour l'instant.

On choisit quand même de suivre le RGAA et les WCAG niveau AA dès le début :

- c'est beaucoup plus simple que de corriger une application déjà terminée ;
- nos personas incluent des personnes âgées et un usage sur téléphone en voiture ;
- si l'application évoluait (vente de services, réservation, partenariat avec une collectivité), elle pourrait devenir concernée.

## Comment faciliter l'accès

Les règles ci-dessous sont celles qui concernent le plus une application de road trip. Chacune renvoie au critère WCAG correspondant (les critères du RGAA reprennent les mêmes règles).

### Couleurs et contrastes

- Le texte doit avoir un contraste d'au moins **4,5:1** avec le fond (3:1 pour le texte en grand). C'est indispensable pour lire l'écran en plein soleil.
- Une information ne doit jamais être donnée **seulement par la couleur**. Par exemple, l'indicateur de synchronisation ne doit pas être juste un point vert ou rouge : il faut aussi un texte ou une icône (« Synchronisé », « Hors ligne »).
- Les deux thèmes (clair et sombre) doivent respecter ces contrastes.

*Référence : WCAG [1.4.1 Utilisation de la couleur](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html), [1.4.3 Contraste minimum](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html), [1.4.11 Contraste du contenu non textuel](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html).*

### Taille du texte et affichage

- L'application doit rester utilisable quand le texte est agrandi à **200 %**, par exemple avec les réglages du téléphone.
- Le contenu doit s'afficher sans défilement horizontal sur un écran de **320 pixels** de large.
- Il ne faut pas bloquer le zoom dans le navigateur, ni forcer une orientation (portrait ou paysage), car un téléphone fixé sur un support en voiture est souvent en paysage.

*Référence : WCAG [1.4.4 Redimensionnement du texte](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html), [1.4.10 Redistribution](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html), [1.3.4 Orientation](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html).*

### Boutons et zones tactiles

- Les boutons doivent faire au moins **24 × 24 pixels** (niveau AA), et idéalement 44 × 44 pixels pour un usage sur téléphone.
- Les actions qui demandent un geste compliqué (glisser une étape pour la déplacer, pincer la carte) doivent aussi être possibles avec un simple appui, par exemple avec des boutons « monter » et « descendre ».

*Référence : WCAG [2.5.8 Taille de la cible (minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html), [2.5.7 Mouvements de glissement](https://www.w3.org/WAI/WCAG22/Understanding/dragging-movements.html).*

### Navigation au clavier

- Toutes les fonctionnalités doivent être utilisables au clavier seul, sans souris (sur ordinateur, c'est le cas des personnes qui ne peuvent pas utiliser leurs mains finement).
- L'élément sélectionné doit toujours être visible (contour de focus), et l'ordre de navigation doit suivre l'ordre logique de la page.
- Une fenêtre ouverte (ajout d'une étape par exemple) ne doit pas piéger le clavier.

*Référence : WCAG [2.1.1 Clavier](https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html), [2.1.2 Pas de piège au clavier](https://www.w3.org/WAI/WCAG22/Understanding/no-keyboard-trap.html), [2.4.7 Visibilité du focus](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html).*

### Lecteurs d'écran

Les personnes aveugles utilisent un lecteur d'écran (VoiceOver sur iPhone, TalkBack sur Android, NVDA sur Windows) qui lit la page à voix haute. Pour qu'il fonctionne :

- utiliser les bonnes balises HTML (`<button>`, `<nav>`, `<h1>` à `<h6>`, `<ul>`) plutôt que des `<div>` cliquables ;
- donner une alternative textuelle aux images et aux icônes seules (une icône « poubelle » doit être lue « Supprimer l'étape ») ;
- indiquer la langue de la page (`<html lang="fr">`) ;
- annoncer les changements qui apparaissent sans rechargement, comme « Voyage synchronisé » ou « Vous êtes hors ligne », avec une zone `aria-live`.

*Référence : WCAG [1.1.1 Contenu non textuel](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html), [1.3.1 Information et relations](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html), [3.1.1 Langue de la page](https://www.w3.org/WAI/WCAG22/Understanding/language-of-page.html), [4.1.3 Messages d'état](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html), [MDN : les régions ARIA live](https://developer.mozilla.org/fr/docs/Web/Accessibility/ARIA/Guides/Live_regions).*

### La carte

Une carte interactive est très difficile à utiliser avec un lecteur d'écran ou au clavier. La carte ne doit donc jamais être le seul moyen d'accéder à l'itinéraire : les étapes doivent aussi être affichées sous forme de **liste textuelle** (nom du lieu, adresse, date, motif du repérage), qui permet de tout consulter et modifier.

*Référence : WCAG [1.1.1 Contenu non textuel](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html).*

### Formulaires

- Chaque champ a une étiquette visible (pas seulement un texte d'exemple qui disparaît quand on écrit).
- Les erreurs sont expliquées en texte, à côté du champ concerné, avec une suggestion pour corriger (« La date de fin doit être après la date de début »).
- Les champs connus (nom, e-mail) utilisent l'attribut `autocomplete` pour être remplis automatiquement.

*Référence : WCAG [3.3.1 Identification des erreurs](https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html), [3.3.2 Étiquettes ou instructions](https://www.w3.org/WAI/WCAG22/Understanding/labels-or-instructions.html), [1.3.5 Identifier la finalité des champs](https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html).*

### Connexion

La connexion ne doit pas demander un effort de mémoire ou de calcul (recopier un code compliqué, résoudre une énigme). Il faut permettre le copier-coller du mot de passe et l'utilisation d'un gestionnaire de mots de passe.

*Référence : WCAG [3.3.8 Authentification accessible (minimum)](https://www.w3.org/WAI/WCAG22/Understanding/accessible-authentication-minimum.html).*

### Animations et temps limité

- Respecter le réglage « réduire les animations » du système avec la requête CSS `prefers-reduced-motion`, pour les personnes sensibles aux mouvements.
- Ne pas imposer de temps limité, par exemple une déconnexion pendant qu'on remplit un formulaire, sans prévenir et sans pouvoir prolonger.

*Référence : WCAG [2.2.1 Réglage du délai](https://www.w3.org/WAI/WCAG22/Understanding/timing-adjustable.html), [2.3.3 Animation résultant d'interactions](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html), [MDN : prefers-reduced-motion](https://developer.mozilla.org/fr/docs/Web/CSS/@media/prefers-reduced-motion).*

### Un contenu simple et cohérent

- Des textes courts et clairs, sans jargon technique (« Vos modifications seront envoyées au retour du réseau » plutôt que « Sync en attente »).
- Les menus et les boutons restent au même endroit sur toutes les pages.
- Des titres de page qui disent où on se trouve (« Étapes – Road trip en Bretagne »).

*Référence : WCAG [2.4.2 Titre de page](https://www.w3.org/WAI/WCAG22/Understanding/page-titled.html), [3.2.3 Navigation cohérente](https://www.w3.org/WAI/WCAG22/Understanding/consistent-navigation.html).*

## Comment vérifier

Les outils automatiques ne détectent qu'une partie des problèmes. Il faut donc combiner :

- **Des outils automatiques :** l'audit Accessibilité de [Lighthouse](https://developer.chrome.com/docs/lighthouse/accessibility/scoring) (intégré à Chrome), [axe](https://github.com/dequelabs/axe-core) ou [WAVE](https://wave.webaim.org/).
- **Des tests à la main :** parcourir l'application au clavier seul, agrandir le texte à 200 %, tester avec un lecteur d'écran ([NVDA](https://www.nvaccess.org/) sur Windows, VoiceOver sur iPhone et Mac, [TalkBack](https://support.google.com/accessibility/android/answer/6283677?hl=fr) sur Android).
- **La méthode du RGAA :** vérifier les critères un par un sur un échantillon de pages, avec la [méthode technique du RGAA](https://accessibilite.numerique.gouv.fr/methode/criteres-et-tests/).

## À faire plus tard

- Choisir des couleurs pour la charte graphique qui respectent les contrastes, en thème clair et sombre.
- Ajouter un audit d'accessibilité automatique dans l'intégration continue.
- Tester les écrans principaux (liste des étapes, carte, partage) avec un lecteur d'écran.
- Rédiger une page accessibilité et une déclaration d'accessibilité, même si ce n'est pas obligatoire pour nous, en s'aidant du [générateur de la DINUM](https://accessibilite.numerique.gouv.fr/obligations/declaration-accessibilite/).
- Suivre la publication du RGAA 5, prévue fin 2026.

## Sources

**Textes officiels**

- [Loi n° 2005-102 du 11 février 2005 pour l'égalité des droits et des chances, la participation et la citoyenneté des personnes handicapées](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000809647), Légifrance
- [Article 47 de la loi n° 2005-102](https://www.legifrance.gouv.fr/loda/article_lc/LEGIARTI000048050213), Légifrance
- [Article 47-1 de la loi n° 2005-102](https://www.legifrance.gouv.fr/loda/article_lc/LEGIARTI000048050174), Légifrance
- [Directive (UE) 2019/882 du 17 avril 2019 relative aux exigences en matière d'accessibilité applicables aux produits et services](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32019L0882), EUR-Lex

**Institutions**

- [Accessibilité numérique : RGAA 4.1.2](https://accessibilite.numerique.gouv.fr/), DINUM
- [Les obligations](https://accessibilite.numerique.gouv.fr/obligations/), DINUM
- [La déclaration d'accessibilité](https://accessibilite.numerique.gouv.fr/obligations/declaration-accessibilite/), DINUM
- [Critères et tests du RGAA](https://accessibilite.numerique.gouv.fr/methode/criteres-et-tests/), DINUM
- [Accessibilité des produits et services](https://www.consilium.europa.eu/fr/policies/accessibility-goods-services/), Conseil de l'Union européenne
- [Handicap et santé](https://www.who.int/fr/news-room/fact-sheets/detail/disability-and-health), Organisation mondiale de la santé

**Normes et documentation technique**

- [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/), W3C
- [Comprendre les critères des WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/), W3C (en anglais)
- [Introduction à l'accessibilité du Web](https://www.w3.org/WAI/fundamentals/accessibility-intro/fr), W3C WAI
- [Accessibilité](https://developer.mozilla.org/fr/docs/Web/Accessibility), MDN
