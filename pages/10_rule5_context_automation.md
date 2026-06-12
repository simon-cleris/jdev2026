---
layout: two-col-slide
clicks: 4
label: Rule 5
title: Automatiser la construction du contexte
desc: Chargement incrémental et récupération autonome — reconstruit à chaque tâche
---

::CardGreen{v-click="1"}

**Fichier racine minimal**

- Lien vers l'index de la documentation
- Lien vers l'index de la spec technique
- Master rules du projet
- Description en une ligne de chaque sous-dossier

::

::CardGreen{v-click="2"}

**CLAUDE.md par sous-dossier**

Chargé automatiquement dès qu'un fichier du dossier est lu ou qu'une commande bash y est exécutée.
Contient la spec fonctionnelle et les choix techniques — jamais de code, jamais de référence de ligne.

::

::CardIndigo{v-click="3"}

**Ces fichiers sont générés par l'agent lui-même**

À partir de la documentation et de la spec, avant toute implémentation.

::

::right::

<ClaudemdExample v-click="4" />
