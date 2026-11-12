# Suivi de la consommation de tokens

Pendant le projet on utilise tous plusieurs IA (Claude Code, Antigravity, claude.ai, etc.) et on voulait savoir combien de tokens chacun consommait. Un token c'est un petit bout de texte de 3 ou 4 caractères, c'est l'unité que les IA utilisent pour compter ce qu'on leur envoie et ce qu'elles répondent.

J'ai d'abord testé deux outils qui existaient déjà, puis on a fini par développer le nôtre.

## 1. OpenUsage

[OpenUsage](https://github.com/janekbaraniewski/openusage) est un outil open source qui s'utilise dans le terminal. Il cherche les IA installées sur la machine (Claude Code, Codex, Cursor, Copilot, Gemini CLI, etc.) et affiche pour chacune les tokens consommés, le coût et le quota restant. Il peut aussi faire un récap par jour, semaine ou mois avec `openusage daily`, `weekly` ou `monthly`.

Il est surtout fait pour Mac et Linux. Sous Windows j'ai essayé deux façons de l'installer et j'ai fait un guide pour chacune, ils sont dans le dépôt [openusage-windows](https://github.com/RoadsPlanner/openusage-windows).

| Méthode | Droits admin | Temps |
|---|---|---|
| Ubuntu avec WSL | oui | environ 20 min, avec un redémarrage |
| Version Windows dans PowerShell | non | environ 5 min |

### Ce que j'ai constaté

Avec WSL, OpenUsage ne voit que ce qui est installé dans Ubuntu. Vu qu'on utilise nos IA sous Windows le tableau de bord restait vide, il aurait fallu tout réinstaller dans Ubuntu. En plus il faut être administrateur et redémarrer le PC.

Avec PowerShell il ne détecte que les IA lancées depuis le terminal comme Claude Code. Par exemple Gemini dans Antigravity n'apparaît pas.

Et l'outil n'est pas très pratique, on se déplace seulement avec le clavier, c'est pas intuitif et les visuels sont durs à lire.

## 2. Un outil de suivi du quota

Le deuxième outil que j'ai installé affichait seulement le pourcentage du quota d'abonnement, par exemple 30 % de la limite de la semaine sur Claude. La plupart des IA le montrent déjà donc ça ne servait pas à grand-chose.

## 3. Tok&Track, notre solution

### Pourquoi on l'a fait nous-mêmes

Aucun des deux ne faisait ce qu'on voulait. Ce qu'il nous fallait :

- que ça marche directement sous Windows, sans WSL et sans être admin
- compter toutes nos IA, même les conversations sur claude.ai
- garder un historique, parce que Claude Code supprime ses conversations au bout de 30 jours
- trier par projet (SAE Trek, SAE Roadtrip, etc.)
- avoir un total par membre et par semaine pour l'équipe
- que l'outil ne consomme pas de tokens lui-même, donc tout en local

Au départ, le 12 octobre, on avait juste un fichier Excel qu'on remplissait à la main. Le 15 on l'a remplacé par un CSV sur GitHub ([suivi-tokens](https://github.com/RoadsPlanner/suivi-tokens)), chacun ajoute sa ligne et une GitHub Action met à jour le tableau de l'équipe. Mais il fallait toujours tout noter à la main, donc j'ai fait un script qui lit directement les données des IA sur le PC. Ce script est devenu l'application Tok&Track le 6 novembre ([TokenTrack](https://github.com/RoadsPlanner/TokenTrack)).

### Ce qu'il permet

![Tableau de bord de Tok&Track](https://raw.githubusercontent.com/RoadsPlanner/TokenTrack/main/docs/apercu.png)

Tok&Track trouve les IA installées sur le PC (applis, outils en ligne de commande, extensions d'IDE) et affiche la consommation par heure, jour, semaine ou mois. On peut filtrer par IA, par projet ou par modèle, séparer l'entrée, la sortie, la réflexion et le cache, et exporter le tableau en CSV.

Il s'installe en un clic sur Windows, Mac et Linux et se met à jour tout seul quand on l'ouvre.

| IA | Ce qui est compté |
|---|---|
| Claude Code, Antigravity, Cline, Roo Code, Kilo Code | tokens réels |
| GitHub Copilot (VS Code) | tokens réels, estimés pour les anciennes requêtes |
| Gemini CLI, OpenAI Codex | tokens réels |
| claude.ai | estimation à partir de l'export des conversations |
| Application Claude | % du quota de l'abonnement |
| Cursor, Windsurf, ChatGPT, Ollama... | détectées, mais sans compteur |

### Limites

Pour claude.ai ce sont des estimations (environ 3,5 caractères par token) parce que l'export ne donne pas le nombre de tokens. Tok&Track ne compte que le PC où il est installé, et il faut l'ouvrir au moins une fois par mois sinon on perd les conversations Claude Code.
