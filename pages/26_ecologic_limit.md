---
layout: ecologic-metric-slide
label: Limite Ecologique
title: Attention aux contre-arguments
---

::Card
<div class="arg-head">
  <span class="arg-title">Certains usages sont déjà locaux</span>
</div>

- L'exemple présenté sera peut-être un jour réalisable par un modèle 32 Go qui tourne en local.
- Pour rappel, certains disaient que la qualité des sorties n'atteindrait jamais celle d'un développeur senior.
::

::Card
<div class="arg-head">
  <span class="arg-title">Pratique déjà obsolète</span>
</div>

- Deux générations de modèles de retard.
- La mode des « loops » : réalisation d'un compilateur par IA autonome en continu pour 20 000 euros de tokens (janvier 2026).
::

::Card
<div class="arg-head">
  <span class="arg-title">Aucune considération pour le ratio efficacité/coût</span>
</div>

- On peut facilement lancer 100 agents en parallèle sur la même tâche et 10 agents chargés de sélectionner la meilleure réponse.
::

<style>
.arg-head {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 0.4rem;
}
.arg-title {
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--text-strong);
}
.slidev-layout .card-md ul { font-size: 0.85rem; }
.slidev-layout .card-md ul li { margin-bottom: 0.15rem; }
</style>
