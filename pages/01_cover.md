---
layout: cover
background: '#0f172a'
class: 'text-center text-white'
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
  "1. risque juridique [...] 2. fiabilité et évaluation [...] 3. maintenabilité [...] Doit-elle être effectuée par IA ? 4. impact environnemental [...] 5. évolution de nos compétences de développement [...] 6. données personnelles [...] 7. données stratégiques envoyées à l'étranger",
  "À ma connaissance il n'y a pas de moyen d'empêcher proprement la lecture de fichiers spécifiques [...], ce qui est très dommageable.",
  "Les IAg peuvent s'assurer que les fonctions qu'elles produisent n'introduisent pas des lignes de code superflues ? des noms de variables incompréhensibles ? de l'existence d'une documentation lisible et claire ? d'une factorisation logique du code ?",
  "le gain de temps (et donc de coûts) est sensé être un des principaux objectif recherché par l'utilisation de l'IAg ce serait ballot qu'au final ça induise plus de temps passé sur des tâches beaucoup moins intéressantes pour un•e développeur•euse",
  "je suis trèèèès dubitatif sur ce que l'utilisation des IAg apporte(rait) de positif VS les aspects négatifs avérés (environnement, social, apprentissage etc.)",
  "L'article ne s'intéresse qu'à la phase d'usage du LLM, c'est affligeant de développer une vision si étroite du problème. On sait que l'impact majeur d'un point de vue limites planétaires est la phase de production ",
  "Bref, bien sûr les LLM sont fascinants, les progrès sont incroyables, mais les adopter c'est adhérer au récit du progrès technique sans les mettre en balance avec les coûts: irresponsable.",
  "actuellement les LLMs produisent du code de faible qualité et qui ne devrait pas aller en prod sans une relecture et des corrections approfondies (à moins que vous suiviez le précepte YOLO et pratiquiez le vibe-coding). Ça vaut aussi bien pour du code \"original\" qu'une réécriture. On peut imaginer que ça va probablement s'arranger, mais jusqu'à quel point ?",
  "certains outils ont [...] une historique de problèmes, bugs et vulnérabilités [...] Ça se traduit par du code, mais aussi par l'expérience acquises par les développeurs, [...] et je doute que le LLM puisse faire quelque chose pour ce dernier point.",
  "Qui est vraiment gagnant [...] actionnaires [...] déjà multimilliardaires et qui vont s'assurer qu'aucune régulation de l'IA ne puisse être mise en place [...] quelque soit l'impact social et environnemental de leur business ?",
  "dans les métiers artistiques, l'IA remplace la partie la plus fun du travail",
  "Peut-être que dans l'avenir, il y a aura des codes dont la source utilisée pour les modifier est la spécification (compilée ensuite par un LLM), et d'autres dont la source utilisée pour les modifier sera le langage de programmation.",
  "les LLM de 2026 sont tout à fait capables de programmer. [...] Pour certains types de tâches, je me sens complètement dépassé.",
  "Je pense qu'il faut bien distinguer deux modes différents d'utilisation de l'IA pour coder: [...] lu voire retravaillé par un humain [...] le cas où on produit un code qui ne sera pas lu par un humain(\"vibe coding\")."
]
</script>

<CitationCloud :interval="8000" :citations="citations" title="Ce que l'IAg peut vraiment faire et ce que ça nous coûte" />
