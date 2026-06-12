---
layout: approach-slide
clicks: 10
label: Mon approche
tagline: Utilisation comme "capacité de raisonnement" sans aucun savoir
paradox: "Paradoxe assumé : un \"raisonnement\" émergent d'un calcul probabiliste ? Ne pas tirer profit de sa base de connaissances ?"
tech:
  - label: Fournir les informations
    body: "Ne pas se fonder sur les données d'entraînement -> Assure la maîtrise et améliore grandement la qualité."
  - label: Fournir les outils
    body: "Détache des données d'entrainement, apporte du déterminisme, améliore la qualité."
  - label: Restreindre le contexte au minimum
    body: "Tout token non pertinent dégrade la qualité."
  - label: Fournir un feedback autonome
    body: "Apporte du déterminisme, améliore la qualité, continue jusqu'à la réussite de la tache."
  - label: Automatiser la construction du contexte
    body: "Pour implémenter les 4 règles précédentes pour chaque tache."
guards:
  - label: "Fixer une limite d'utilisation"
    body: "Analogie data 3G/4G/5G : une limite fixe évite l'effet rebond à chaque nouvelle version."
  - label: "Utiliser que pour ce qu'on sait faire"
    body: "Accélère ce qu'on peut faire soi-même mais ne jamais l'utiliser pour une tache que l'on ne maîtrise pas."
  - label: "Contenir le pouvoir d'action"
    body: "Supervision de chaque sortie, ou containerisation pour les process autonomes."
  - label: Attention aux données sensibles
    body: "Evident."
---
