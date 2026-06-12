---
layout: rule-slide
clicks: 3
label: Rule 2
title: Fournir les outils
desc: Détache des données d'entraînement, apporte du déterminisme, améliore la qualité
---

::CardGreen{v-click="1"}

**Accès SSH à l'instrument** `accès direct au hardware`{.badge-green}

L'agent peut interagir avec l'instrument réel pour valider le comportement.

::

::CardGreen{v-click="2"}

**Accès Bash au poste de développement** `garde-fou`{.badge-green}

Toutes les commandes doivent être approuvées —
sauf `find`{.badge-muted} et `read`{.badge-muted} à l'intérieur du projet.

::

::CardAmber{v-click="3"}

**Garde-fou :** contenir le pouvoir d'action — supervision de chaque sortie, approbation explicite de toute commande destructive.

::
