# Contexte projet - SaaS Aide Devoirs (MVP)

## Etat actuel (snapshot)

- Vision : aider les enfants a faire leurs devoirs via un parcours IA guide, puis donner aux parents une vue claire pour decider de continuer ou refaire.
- Utilisateurs : `ENFANT` (parcours guide + soumission) et `PARENT` (lecture score/temps/progression + decision).
- Flux metier MVP cible : saisie devoir (mock/manual) -> `IA_TUTEUR` (plan d'action) -> soumission enfant (texte + photo) -> `IA_CORRECTEUR` (score + feedback) -> decision parent.
- Priorites produit : auth + roles d'abord, puis pipeline IA, puis stockage des soumissions/scores, puis interfaces minimales, puis connecteurs (apres MVP).

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
