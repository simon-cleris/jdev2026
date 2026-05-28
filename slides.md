---
theme: default
title: Ce que l'IA peut vraiment faire et ce que ça nous coûte
background: '#0f172a'
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
layout: none
---

<script setup>
const citations = [
  "Aujourd'hui, il n'y plus grand chose de sûr...",
  "est-ce que ce sont des informations vérifiées, ces milliers de vulnérabilité ? ou juste de la com parce que plus personne ne va vérifier, maintenant qu'il suffit de demander à un chatbot?",
  "Autrement dit, entre de mauvaises pattes, ça peut faire mal...mais entre de bonnes pattes, ça peut aider ;-)",
  "un repo réécrit par une IA [...] réduit à néant le gain social espéré par l'effort investi    [...], il prive des dev junior de l'opportunité de montrer publiquement leurs compétences.",
  "les conséquences sociales et matérielles du vibe coding sont déjà bien concrètes, avec pour la première fois une précarité des ingé en informatique qui progresse (dans un contexte aussi de baisse de la demande post-covid).",
  "Et à titre personnel cette situation m'inquiète d'autant plus quand je vois que des grand chercheurs ou chercheuses de l'IA préfèrent disserter sur des conséquences [...] alors que des gens subissent déjà les conséquences matérielles bien concrètes de cette technologie",
  "[...] sommes nous en train de tomber dans une forme de dépendance avec les agents IA?",
  "1. risque juridique [...] 2. fiabilité et évaluation [...] 3. maintenabilité [...] Doit-elle être effectuée par IA ? 4. impact environnemental [...] 5. évolution de nos compétences de développement [...] 6. données personnelles [...] 7. données stratégiques envoyées à l'étranger"
]
</script>

<CitationCloud :interval="8000" :citations="citations" />
