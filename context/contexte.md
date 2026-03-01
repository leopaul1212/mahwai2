[FILE] context/contexte.md — Contexte operationnel consolide (pour IA/dev)
Workflow: Lu au demarrage d'une nouvelle session pour comprendre l'etat du projet, les invariants, les sources de verite et la prochaine etape utile.
Inputs: `context/global.md`, `context/avancement.md`, `context/fonctionnalites.md`, `context/stacktechnique.md`, `context/tacheaccomplie.md`, decisions produit.
Outputs: snapshot courant + invariants + historique des decisions + prochaines actions/test.
Decision tree:
- Input (besoin d'avancer)
  - if priorites definies dans `context/avancement.md` -> suivre l'"Ordre de dev recommande" et les tests associes
  - else -> relire `context/global.md` + `context/fonctionnalites.md` pour reposer une roadmap
- -> appliquer la prochaine feature prioritaire en respectant stack/invariants
Structure: Etat actuel, Sources de verite, Invariants/contraintes, Historique des changements

# Contexte projet - SaaS Aide Devoirs (MVP)

## Etat actuel (snapshot)

- Vision : aider les enfants a faire leurs devoirs via un parcours IA guide, puis donner aux parents une vue claire pour decider de continuer ou refaire.
- Utilisateurs : `ENFANT` (parcours guide + soumission) et `PARENT` (lecture score/temps/progression + decision).
- Flux metier MVP cible : saisie devoir (mock/manual) -> `IA_TUTEUR` (plan d'action) -> soumission enfant (texte + photo) -> `IA_CORRECTEUR` (score + feedback) -> decision parent.
- Priorites produit : auth + roles d'abord, puis pipeline IA, puis stockage des soumissions/scores, puis interfaces minimales, puis connecteurs (apres MVP).
- Etat d'avancement : projet au stade documentation/cadrage MVP, backlog present dans `context/avancement.md`.

## Sources de verite (docs internes)

- Vue d'ensemble stable : `context/global.md`
- Backlog + ordre de dev + tests a faire : `context/avancement.md`
- Fonctionnalites (liste metier) : `context/fonctionnalites.md`
- Stack technique (reference) : `context/stacktechnique.md`
- Carte des fichiers de contexte : `context/planprojet.md`
- Journal des actions : `context/tâcheaccomplie.md`

## Invariants / contraintes deja posees

- Auth : Auth.js (NextAuth) avec roles `PARENT | ENFANT`.
- IA : appels uniquement cote serveur, sorties JSON strictes, prompts versionnes.
- Stockage photo (MVP) : local dans `/public/uploads` (evolution cloud plus tard).

## Historique des changements (decisions et ajouts majeurs)

## [2026-03-01] Prochaine etape recommandee - Implementer Auth + roles (MVP)
- Contexte : la priorite active est "auth avant tout le reste" pour securiser routes/APIs des le debut.
- Resume : demarrer l'implementation par Auth.js (NextAuth) + roles `PARENT | ENFANT`, avec protection role-based sur pages et endpoints.
- Impact : toutes les futures features (pipeline IA, uploads, devoirs, dashboards) devront s'appuyer sur la session et les controles de role cote serveur.
- A tester : login, gestion session, protection routes/pages, verification role serveur (tests aligns avec `context/avancement.md`).

## [2026-03-01] Plan de developpement MVP - SaaS Aide Devoirs
- Contexte : besoin de structurer le MVP autour du pipeline IA et des connecteurs externes.
- Resume : creation d'un backlog detaille dans `context/avancement.md` avec priorites, ordre de dev et cas de test associes pour chaque feature.
- Impact : clarifie la sequence de travail pour le workflow devoir -> tutorat IA -> soumission enfant -> correction IA -> decision parent.
- A tester : coherence du backlog et demarrage des phases (note : la priorite a ensuite ete changee en auth-first, voir entree suivante).

## [2026-03-01] Changement de priorite - Auth en premier
- Contexte : decision produit de demarrer par la securisation des acces avant le pipeline IA.
- Resume : mise a jour de l'ordre de developpement dans `context/avancement.md` pour positionner `Auth + roles` en etape 1.
- Impact : les ecrans et endpoints MVP doivent etre construits avec gestion de session et controle de role des le debut.
- A tester : login, gestion session, protection routes et APIs, liaison parent/enfant minimale.

## [2026-03-01] Ajout de la reference stack technique
- Contexte : besoin de disposer d'une source claire pour connaitre les technos retenues.
- Resume : creation du fichier `context/stacktechnique.md` avec description des outils et de leur role dans le MVP.
- Impact : facilite l'alignement produit/technique et evite les choix contradictoires pendant le developpement.
- A tester : coherence entre la stack documentee et les dependances/code reels lors des prochaines implementations.

## [2026-03-01] Ajout d'un fichier de description des fonctionnalites
- Contexte : besoin d'une liste metier lisible des fonctionnalites a couvrir (sans entrer dans le backlog technique).
- Resume : creation de `context/fonctionnalites.md` (fonctionnalites coeur MVP + apres MVP + critere de reussite).
- Impact : sert de reference produit pour verifier que `context/avancement.md` couvre bien tout le flux.
- A tester : coherence entre `context/fonctionnalites.md`, `context/global.md` et le flux cible de `context/avancement.md`.
