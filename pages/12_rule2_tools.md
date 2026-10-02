---
layout: rule-slide
icon: i-carbon:tools
clicks: 4
label: Règle 2
title: Fournir les outils
desc: Détache des données d'entraînement, apporte du déterminisme, améliore la qualité
---

::Card{v-click="1"}

**Accès Bash au poste de développement**

::

::Card{v-click="2"}

**Accès SSH à l'instrument**

::

::Card{v-click="3"}

**Accès aux outils agentiques de Claude Code**

::

::CardOutline{v-click="4"}

Supervision de chaque sortie, approbation explicite de toute commande.

::

<style scoped>
.card-md {
  padding: 1.5rem 2rem;
}
.card-md p:first-child > strong:only-child {
  font-size: 1.35rem;
  margin-bottom: 0;
}
.card-orange-outline.card-md p {
  font-size: 1.1rem;
}
</style>

<!--
[click] Accès Bash au poste de développement : équivalent à la majorité de ce qu'un utilisateur peut faire.
[click] Accès SSH à l'instrument : l'agent peut interagir avec l'instrument réel pour valider le comportement.
[click] Accès aux outils agentiques de Claude Code : peut être une contrainte lorsqu'on veut plus de personnalisation. Simplifie l'automatisation du contexte.
[click] Supervision de chaque sortie, approbation explicite de toute commande.
-->
