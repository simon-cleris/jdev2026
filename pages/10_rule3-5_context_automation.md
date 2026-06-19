---
layout: rule-slide
clicks: 5
zoom: 0.8
label: Règles 3 et 5
title: Automatiser la construction du contexte minimal
desc: Chargement incrémental (claude.md) et récupération autonome (skills)
---

::Card{v-click="1"}

**Un Fichier global toujours chargé** 
- Lien (seulement le lien) vers l'index de la documentation (spécification fonctionnelle et technique)
- Règles global du projet (le code contient lui même nos préférence)
- Description en une ligne de chaque sous-dossier

::

::Card{v-click="2"}

**Un Fichier chargé par sous-dossier**

- Chargé automatiquement dès qu'un fichier du dossier est lu ou qu'une commande bash y est exécutée.
- Contient (entièrement) la spec fonctionnelle et les choix techniques des scripts du dossier (jamais de code)
- Description en une ligne de chaque sous-dossier

::

::Card{v-click="3"}

**Générés par l'agent lui-même**

- À partir de la documentation, avant toute implémentation (simplifie le controle)
::

:: CardOutline{v-click="4"}
Ce système permet de vider le contexte entre chaque tâche. Le contexte minimal est reconstruit automatiquement (sans coût). Garantit la qualité et une faible utilisation en token (obligatoire pour notre limite d'utilisation).
::