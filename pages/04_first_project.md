---
layout: error-slide
clicks: 6
context: Juin 2025 — Génération de rapports LaTeX à partir de données actualisées
title: Premier projet — les erreurs
---

::CardRed{v-click="1"}

**Librairie non maîtrisée** `pydantic-ai`{.badge-red}

→ Bad patterns non détectés, propagés silencieusement dans tout le code

::

::CardRed{v-click="2"}

**Contexte non structuré** `codebase entière dans le prompt`{.badge-red}

→ Coût élevé, duplication de code, mauvaise qualité

::

::CardRed{v-click="3"}

**Pas de spec fonctionnelle** `démarrage sans définition complète`{.badge-red}

→ Duplication de code, périmètre instable

::

::CardRed{v-click="4"}

**Spec technique insuffisante** `choix architecturaux laissés à l'IA`{.badge-red}

→ Overengineering incontrôlé

::

::CardRed{v-click="5"}

**Feedback manuel** `validation par test humain uniquement`{.badge-red}

→ Mauvaise qualité et temps perdu en boucles de correction

::

::CardGreenOutline{v-click="6"}

Malgré tout : projet simple, objectif atteint, délai négligeable. Sur un projet plus grand...

::
