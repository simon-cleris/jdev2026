ajouter le changement dh'abiture pour adatper l'outil au mieux à l'ia parallele machine a laver

Rajouter le fait que le plan demande le plus gros LLM mais la c'est nous qui faisons le plan.

Rajouter le terme AI factory

Parler du fais qu'il faut nuancer entre lui dire exactement comment faire et lui laisser la possiblité de faire mieux que ce que l'on pense -> séparé l'étape

nuancé en fonction de la difficulté de la tache (pour une ia par la difficulté pour un humain)

trouver le bon endroit ou mettre le curseur poru ne pas rester dans la planifciation infiniment (évident pour moi mais je me rend compte que c'est peut être pas si simple)

différent agent pour différent moment (le plus gros est poru la planification)

# Ajout de slides

## Slide definition des termes

#### Prompt Engenerring :

« Comment formuler au mieux l'instruction ? »

#### Context Engineering :

« Comment fournir automatiquement à l'agent
les bon prompts au bon moment ? »

#### Harness Engineering :

« Comment construire l'environnement dans lequel
l'agent peut agir : outils, état, contraintes,
feedback, tests, permissions… ? » C'est ici que vivent les loops pour ceux qui connaissent.

#### Factory Engineering :

« Comment construire le système complet qui au seins duquel des agents réalise directement le produit final ? »

Article qui a été salué par la communauté pour mettre tout ça sur papier appliqué au développement informatique : Osmani, A., Saboo, S., & Kartakis, S. (2026).  *The new SDLC with vibe coding: From ad-hoc prompting to agentic engineering* . Google.

#### Vibe coding VS agentic engineering :

diff_vibe_agentic.png

## Slide comment obtenir ces outils : deux solutions :

### Ragarennes / Albert AI

fourni une API mais pas au niveau

### Vibe CLI

Voici comment installer :

Hello,

Voici le lien ou on installe l'extension : [https://chat.mistral.ai/code/extensions](https://chat.mistral.ai/code/extensions)

Mais basiquement vous faite dans un terminal (linux) : curl -LsSf [https://mistral.ai/vibe/install.sh](https://mistral.ai/vibe/install.sh) | bash
Une fois installé ouvrir un nouveau terminal et faire : vibe --setup
Vous
 choisissez votre thème ensuite vous choisissez bien "Launch browser"
puis "Mistral AI" ça va ouvrir votre navigateur et vous aurez plus qu'à
rentrer votre adresse cnrs et ça vous redirige sur Janus

Voila !

Pour
 lancer il suffit maintenant de taper vibe dans un terminal dans le
dossier ou vous voulez travailler ! Si vous ne savez pas par ou
commencer voici la doc : [https://docs.mistral.ai/vibe/code/cli/work-with-cli](https://docs.mistral.ai/vibe/code/cli/work-with-cli)

ENJOY

## Slide actualité sur l'IA

Faire une frise choronologiques des prouesses les plus maraquantes en IA depuis 2025. (par exemple mettre le cas navier stokes ou encore le compilateur c en rust one shot,frontier modèle qui font des cartes electroniques (70% de réussistes) -> vérifier et mettre la source...) chercher sur le net

Parler de Jev rapidement et sa révolution pour l'automatisation

Parler de Sonnet 5.5 qui concrruance les meilleurs modèles pour deux fois moins chère et 2 fois plus rapide (trouver chiffres exact)
