Contexte : 

On va maintenant illustrer l'implémentation de cette approche sur quelques projets choisi. 

Application code embarqué instrument scientifique.

Contexte : développement d'un nouvel instrument.

Approche Développement opérationnel assisté par IA

Rule 1 : Fournir les informations

première étape : la documentation = la spécification.

Rédaction de la spécification fonctionnelle qui servira également de documentation pour les logiciels embarqué.
En annexe les manuels techniques de touts les composants hardware.
Sous forme de .md et fournis aux commanditaires de l'instrument sous forme de site internet pour reboucler avec eux en conformité avec l'approche devops.
(Mettre animation du site en illustration)

Rédaction de la spécification technique, choix technologiques et architecturaux pour répondre aux cahiers des charges.

Rule 2 : Fournir les outils

Accès ssh à l'instrument
Accès bash au poste de développement (toutes commandes doit être approuvé sauf find / read à l'intérieur du projet)

Rule 3 et 4 : Construction automatique du context minimum

Ce qui suit est réalisé pour chaque tache (a chaque tache le context est clear)
On se fonde sur deux principes, le chargements de contexte incrémental et la récupération de contexte autonome.
On va systématiquement chargé le context de l'agent avec un fichier très minimal.
Dans ce fichier on va lui mettre :
- un lien vers l'index de la documentation du projet
- un lien vers l'index de la specification technique
- nos master rules (exemple : Max 500 lines per code file, - **One owner per hardware.** A module owns its hardware exclusively. All other modules access it via the event bus, never directly.) Attention pas besoin d'en mettre trop car le code contient en lui lui même nos préférence si l'on fait bien attention au première implémentation.
- une description en une ligne de ce qu'il y a dans chaque sous-dossier. (- `common/` — internal library shared by all instruments)

Dans chaque sous dossier on a un fichier qui charge systématiquement le context si un fichier de ce dossier ou d'un sous-dossier est lu par l'agent. ou s'il réalise la moindre commande bash dans ce dossier. il contient :
- la spec fonctionnel et choix technique des scripts du dossiers (Jamais de code, jamais de référence de ligne)
ex : 

---
## common/state_machine.py — State Machine

Service — computes flight phase from aircraft speed, publishes state transitions and flight events.

### State machine Behaviour

- Subscribes to: `AircraftData`, `ModuleDisconnected` (for CRITICAL modules → ERROR)
- Computes state based on speed thresholds:
  - **STOPPED**: speed < 3 knots
  - **MOVING**: 3 <= speed < 50 knots
  - **VERTICAL_PHASE**: 50 <= speed < 250 knots
  - **CRUISE**: speed >= 250 knots
  - **STANDALONE**: aircraft data unavailable 60s + `standalone_mode.enabled = true`
  - **ERROR**: aircraft data unavailable 60s + `standalone_mode.enabled = false`, OR critical module DISCONNECTED
- Publishes: `StateTransition`, `INIT`, `INIT_IN_FLIGHT`, `LEVEL_OFF`, `LANDING`
- **Publishes flight events**:
  - `INIT`: at boot if speed < 3 knots; after LANDING when STOPPED >= 3 min AND >= 10 min since last LANDING AND speed < 50 knots since last LANDING
  - `INIT_IN_FLIGHT`: at boot if speed >= 3 knots
  - `LEVEL_OFF`: transition VERTICAL_PHASE -> CRUISE or MOVING -> CRUISE
  - `LANDING`: transition VERTICAL_PHASE -> MOVING or CRUISE -> MOVING
- **Data loss detection**: 60s without valid ground_speed (20 consecutive missing at 0.25 Hz) → STANDALONE or ERROR depending on config
- **Data recovery**: immediate transition to speed-based state
- Ignores `maintenance_mode` flag — continues operating in MAINTENANCE mode

---

- Une description en une ligne de ce qu'il y a dans chaque sous-dossier.

Bien sur ces fichiers automatiquement chargé sont construit par l'agent lui même à partir de la documentation et de la spécification avant implémentation du code. 
Grâce à ce système on va supprimer tout contexte entre deux tache même si elle sont très lié ou similaire. Rule 3. On s'en fiche car on sait que tout le contexte sera automatiquement regénérer. (en + c'est obligatoire vue notre règles de limite d'utilisation).



Plan d'implémentation, rédaction d'un plan d'implémentation en phase indépendante :

- Création ou update du fichier d'instruction
- feedback humain

Rule 3 : Clear du context

- template d'un driver
- drivers (réel et mock)
- tests d'intégration
- feedback du test

Rule 3 : Clear du context

- Création ou update du fichier d'instruction
- feedback humain

Rule 3 : Clear du context

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