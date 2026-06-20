Application code embarqué instrument scientifique.

Contexte : développement d'un nouvel instrument.

Approche Développement opérationnel assisté par IA

première étape : la documentation = la spécification.

Rédaction de la spécification fonctionnelle qui servira également de documentation pour les logiciels embarqué. 
En annexe les manuels techniques de touts les composants hardware. 
Sous forme de .md et fournis aux commanditaires de l'instrument sous forme de site internet pour reboucler avec eux en conformité avec l'approche devops. 

Mettre animation du site en illustration. 

Rédaction de la spécification technique, choix technologiques et architecturaux pour répondre aux cahiers des charges.


Plan d'implémentation, rédaction d'un plan d'implémentation en phase indépendante :

- template d'un driver
- drivers (réel et mock)
- tests d'intégration
- feedback du test

- fichier de spécification dédié au module (claude.md)
- template d'un module
- module non rataché au hardware pour répondre a une ou des spécification
- test de validation de spécification
- feedback du test (choix sur drivers réel ou mock)

- test end to end (plusieurs simulation de vol de configuration différentes)
- feedback du test (choix sur drivers réel ou mock)

Mettre diagramme d'architecture

Résultat: 
- un logiciel maîtrisé réalisé en 4 mois et fiable. (car hardware monté au fur et a mesure)
- optimisé pour que la maintenance sois assisté par IA (context dynamique optimisé et toutes les informations disponibles)

Note : important les premiers scripts de code doivent être réalisé de manière perfectionniste. Autant le template que les habitudes et préférence de code car il seront le modèle pour la suite. 