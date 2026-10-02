---
layout: title-content-slide
label: Limite Ecologique
title: Ce que l'estimation ne compte pas
---

<div class="grid grid-cols-3 gap-4">
  <StatCard value="~10" unit="trillions requêtes/an" label="Volume"></StatCard>
  <StatCard value="50" unit="TWh" label="IA en 2025"></StatCard>
  <StatCard value="5" unit="Wh / requête" label="×20 l'estimation Google"></StatCard>
</div>

::Card
**Le coût par requête est une mauvaise métrique**
::

::Card
Simple mise en perspective qui n'enlève rien au bilan précédent : le GIEC estime que **devenir végétarien réduit en moyenne, au niveau mondial, les émissions de GES de 10 %**.
::

::div{.slide-sources}
**Sources**
- (1) OpenAI — *OpenAI's new economic analysis* (22 juillet 2025) — https://openai.com/global-affairs/new-economic-analysis/
- GIEC/IPCC — *Climate Change and Land*, Chapitre 5 (2019)
::

<style>
.slidev-layout .slide-sources { bottom: 2.25rem; }
.slidev-layout .stat { padding: 1rem 1.25rem; }
.slidev-layout .stat .value { font-size: 3rem; }
.slidev-layout .stat .unit { font-size: 1.15rem; }
.slidev-layout .stat .label { font-size: 0.8rem; }
.slidev-layout .card-left-orange.card-md { padding: 1rem 1.5rem; }
.slidev-layout .card-md p:first-child > strong:only-child { font-size: 1.25rem; margin-bottom: 0.25rem; }
.slidev-layout .card-md p:last-child { font-size: 1.1rem; }
</style>

<!--
Volume : ChatGPT ~2,5 Mds requêtes/jour (1), environ 10 % du marché (OpenRouter 2025).

IA en 2025 : l'estimation Google ne compte que l'inférence.

×20 l'estimation Google : 20 % de la batterie d'un smartphone. Hypothèse : chaque requête contribue à l'essor global de l'IA.

Le coût par requête est une mauvaise métrique :
- Le coût unitaire va baisser, mais le coût total va exploser.
- Il vaut mieux regarder la consommation moyenne par utilisateur (sujette à l'effet rebond, comme pour la 3G/4G/5G).
-->
