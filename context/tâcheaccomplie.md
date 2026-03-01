- **[2026-03-01] Ajout d'une fiche globale projet**  
  - But : disposer d'un document unique, rapide a lire, qui decrit le projet dans son ensemble.
  - Description : creation de `context/global.md` (vision, probleme, utilisateurs, flux MVP, priorites, stack, etat) et mise a jour de la carte projet/regles associees.
  - Fichiers modifies : `context/global.md`, `context/planprojet.md`, `context/rulesIA.md`, `context/tâcheaccomplie.md`
  - Tests : verification documentaire de coherence entre fichiers de contexte / A tester : maintien de l'alignement global lors des prochains changements de priorite

- **[2026-03-01] Repriorisation du plan MVP vers Auth d'abord**  
  - But : aligner la roadmap avec la decision de commencer par l'authentification.
  - Description : reorganisation de l'ordre de developpement pour placer `Auth + roles` en etape 1, puis pipeline IA et le reste.
  - Fichiers modifies : `context/avancement.md`, `context/contexte.md`, `context/tâcheaccomplie.md`, `context/planprojet.md`, `context/rulesIA.md`
  - Tests : verification documentaire de coherence / A tester : validation technique login, sessions, controles d'acces role-based

- **[2026-03-01] Creation du fichier de stack technique**  
  - But : centraliser les choix techniques du projet dans un document unique.
  - Description : ajout de `context/stacktechnique.md` avec la stack front, back, DB, auth, IA, securite, monitoring et architecture cible.
  - Fichiers modifies : `context/stacktechnique.md`, `context/planprojet.md`, `context/avancement.md`, `context/tâcheaccomplie.md`, `context/contexte.md`, `context/rulesIA.md`
  - Tests : relecture de coherence entre docs / A tester : alignement continu de la stack documentee avec l'implementation reelle
