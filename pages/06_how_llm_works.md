---
layout: llm-slide
clicks: 11
---

::intro::

<div v-click="0" class="card-indigo shrink-0 text-center card-md">

**Mécanique**{.t-label style="color: var(--indigo);"}

Prédit le token suivant le plus probable compte tenu des tokens précédents et de ses données d'entraînement

Pas de raisonnement, pas de compréhension : de la statistique à partir d'une immense base de données

</div>

::transition::

<div v-click="1" class="text-center text-base font-semibold shrink-0" style="color: #cbd5e1;">
  Ce qui nous fait naturellement penser qu'on peut l'utiliser comme <span style="color: var(--text-strong);">base de connaissance</span>
</div>

::default::

::CardRed{v-click="2"}
**Dépendance / Dette technique**
Analogie Google effect : déléguer atrophie la mémoire et les réflexes.
::

::CardRed{v-click="3"}
**Hallucination / Qualité imprévisible**
Le modèle invente avec confiance et ne signale pas ses erreurs.
::

::CardRed{v-click="4"}
**Dette technique**
Du code non maîtrisé s'accumule, les bad patterns se propagent.
::

::CardRed{v-click="5"}
**Perte de compétences**
On ne sait plus faire ce qu'on délègue.
::

::CardRed{v-click="6"}
**Qualité imprévisible**
Sans expertise pour juger la sortie, impossible de détecter les erreurs.
::

::CardRed{v-click="7"}
**Risque juridique**
Droits sur les sorties incertains, données envoyées à des tiers.
::

::CardRed{v-click="8"}
**Données exposées**
Données personnelles et stratégiques chez un fournisseur privé.
::

::CardRed{v-click="9"}
**Impact environnemental**
Coût énergétique massif à l'entraînement et à l'inférence.
::

::CardRed{v-click="10"}
**Dépendance fournisseur**
Couplage fort à un acteur privé hors de tout contrôle.
::
