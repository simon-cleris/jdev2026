---
layout: title-content-slide
label: Actualité
title: "Septembre 2026 : deux annonces à suivre"
clicks: 2
zoom: 0.9
---

<div class="grid grid-cols-2 gap-6 items-start">

<div v-click="1" class="flex flex-col gap-3">

<div class="t-label" style="color: var(--orange);">Jev, TypeSafe AI (15 septembre)</div>

<div class="card-left-orange card-md">

**Un modèle qui ne converse pas : il décide**{.badge-orange}

On lui envoie un état et des questions typées ; il renvoie un choix, un score ou une probabilité, sans texte ni code.

</div>

<StatCard value="200x" unit="plus rapide" label="Annonces de l'éditeur, tâches de classification">
Environ 400 fois moins cher qu'un LLM comparable, avec une latence de 70 à 500 ms.
</StatCard>

</div>

<div v-click="2" class="flex flex-col gap-3">

<div class="t-label" style="color: var(--orange);">Claude Sonnet 5.5, Anthropic (28 septembre)</div>

<div class="grid grid-cols-2 gap-3">

<StatCard value="2x" unit="moins cher" label="Prix par million de tokens">
2 $ en entrée et 10 $ en sortie, contre 4 $ et 20 $ pour Opus 5.5.
</StatCard>

<StatCard value="+30" unit="% vitesse" label="Génération de sortie">
Plus rapide que Sonnet 5 ; jusqu'à 30 % de coût en moins par tâche.
</StatCard>

</div>

<CardOutline>

**Au niveau d'Opus 5.5 sur plusieurs benchmarks**

Terminal-Bench 4.0 : 70,6 % contre 66,4 %. GDPval-AA : 1844 contre 1846.

</CardOutline>

</div>

</div>

::div{.slide-sources}
- Forbes (2026). *Why everyone is talking about Jev, the AI that doesn't chat*. forbes.com, 22 septembre 2026
- VentureBeat (2026). *Anthropic launches Claude Sonnet 5.5*. venturebeat.com
::

