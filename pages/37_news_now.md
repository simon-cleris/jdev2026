---
layout: title-content-slide
label: Actualité
title: "On n'arrête pas le « progrès »"
clicks: 2
zoom: 1
---

<div class="grid grid-cols-2 gap-4 items-stretch" style="margin-block: auto; margin-bottom: 8rem;">

<div v-click="1" class="flex flex-col gap-3">

<div class="t-label" style="color: var(--orange);">Jev, TypeSafe AI (15 septembre)</div>

<div class="card-left-orange card-md">

**Un modèle qui ne converse pas : il décide**{.badge-orange}

</div>

<div class="grid grid-cols-2 gap-3">

<StatCard value="200x" unit="plus rapide" label="Annonce de l'éditeur" />

<StatCard value="400x" unit="moins cher" label="Qu'un LLM comparable" />

</div>

</div>

<div v-click="2" class="flex flex-col gap-3" style="border-left: 1px solid var(--navy-border); padding-left: 1.25rem;">

<div class="t-label" style="color: var(--orange);">Claude Sonnet 5.5, Anthropic (28 septembre)</div>

<div class="grid grid-cols-2 gap-3">

<StatCard value="30" unit="% moins cher" label="Coût par tâche" />

<StatCard value="+30" unit="% vitesse" label="Génération de sortie" />

</div>

<CardOutline>

**Au niveau d'Opus 5.5 sur plusieurs benchmarks**

</CardOutline>

</div>

</div>

::div{.slide-sources}
- Forbes (2026). *Why everyone is talking about Jev, the AI that doesn't chat*. forbes.com, 22 septembre 2026
- VentureBeat (2026). *Anthropic launches Claude Sonnet 5.5*. venturebeat.com
::

<!--
[click] Jev (TypeSafe AI, 15 septembre) : un modèle qui ne converse pas, il décide. On lui envoie un état et des questions typées ; il renvoie un choix, un score ou une probabilité, sans texte ni code. 200x plus rapide sur des tâches de classification (annonces de l'éditeur), environ 400 fois moins cher qu'un LLM comparable, latence de 70 à 500 ms.
[click] Claude Sonnet 5.5 (Anthropic, 28 septembre) : 2 $ en entrée et 10 $ en sortie par million de tokens, contre 4 $ et 20 $ pour Opus 5.5. Plus rapide que Sonnet 5 (+30 % de vitesse de génération), jusqu'à 30 % de coût en moins par tâche. Au niveau d'Opus 5.5 sur plusieurs benchmarks : Terminal-Bench 4.0 70,6 % contre 66,4 %, GDPval-AA 1844 contre 1846.
-->
