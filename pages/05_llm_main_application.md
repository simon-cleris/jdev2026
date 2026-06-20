---
layout: llm-slide
clicks: 4
---

::intro::

<div class="card-navy shrink-0 text-center card-md">

**Fonctionnement d'un LLM (simplifié)**{.t-label style="color: var(--orange);"}

Prédit le token suivant le plus probable compte tenu des tokens précédents et de ses données d'entraînement

Pas de raisonnement, pas de compréhension : de la statistique à partir d'une immense base de données

</div>

::transition::

<div v-click="1" class="text-center text-base font-semibold shrink-0" style="color: #cbd5e1;">
 L'utilisation la plus courante d'un LLM, c'est de l'utiliser pour son "savoir"
</div>

::default::

::Card{v-click="2"}
**Perte de compétences** : On n'apprend pas si l'on délègue.
::

::Card{v-click="3"}
**Hallucination** : Le modèle invente avec confiance.
::

::Card{v-click="4"}
**Qualité imprévisible** : Pas d'expertise pour juger la sortie.
::
