### avancement.md
- Role : backlog principal du MVP avec priorites et statut de test.
- Contrat Input/Output : Inputs priorites produit + stack + contraintes -> Outputs liste de features cochees avec "a tester" et scenarios de verification.
- Ne pas faire : supprimer des items metier sans justification, melanger des taches hors MVP prioritaire, enlever les tests a effectuer.
- Modifier seulement si : nouvelle feature, changement de priorite, avancement d'implementation ou precision des tests.
- Tests associes : revue coherence roadmap, alignement ordre de dev (incluant auth-first si decide), couverture des points critiques pipeline IA.

### planprojet.md
- Role : representer la carte des fichiers de contexte et leur responsabilite.
- Contrat Input/Output : Inputs structure projet actuelle -> Outputs arbre projet avec inputs/outputs de chaque fichier.
- Ne pas faire : documenter des fichiers inexistants, decrire des roles vagues sans input/output.
- Modifier seulement si : ajout/suppression de fichiers de contexte ou changement de role.
- Tests associes : verification manuelle des chemins et des descriptions.

### tacheaccomplie.md
- Role : journal chronologique des actions effectuees.
- Contrat Input/Output : Inputs actions realisees + fichiers modifies + tests -> Outputs trace exploitable de l'historique.
- Ne pas faire : laisser des entrees sans date, oublier les fichiers modifies, omettre "A tester" quand necessaire.
- Modifier seulement si : une action est terminee ou un suivi doit etre corrige.
- Tests associes : controle de presence des 5 champs (But, Description, Fichiers modifies, Tests, A tester).

### contexte.md
- Role : synthese globale du projet et de son etat courant pour les prochaines IA.
- Contrat Input/Output : Inputs decisions et changements majeurs -> Outputs contexte consolide avec impacts workflows.
- Ne pas faire : garder des pointeurs obsoletes vers des fichiers inexistants, accumuler du texte sans impact concret.
- Modifier seulement si : changement de cap produit, nouvelle phase, evolution majeure du workflow.
- Tests associes : verification de coherence entre contexte, avancement et tacheaccomplie.

### global.md
- Role : fiche globale stable qui decrit le projet (vision, utilisateurs, flux, priorites, etat).
- Contrat Input/Output : Inputs cadrage produit et priorites actives -> Outputs vue d'ensemble rapide et partageable.
- Ne pas faire : dupliquer tout le backlog, contredire `avancement.md` ou `stacktechnique.md`, ajouter des details techniques instables.
- Modifier seulement si : evolution de la vision, changement d'utilisateurs cibles, ajustement du flux MVP ou des priorites globales.
- Tests associes : verification de coherence avec `contexte.md`, `avancement.md` et `stacktechnique.md`.

### stacktechnique.md
- Role : decrire la stack technique officielle du projet et l'usage de chaque technologie.
- Contrat Input/Output : Inputs choix techniques (frontend, backend, DB, auth, IA, securite) -> Outputs reference unique et exploitable par les dev/IA.
- Ne pas faire : ajouter des technos non validees, decrire des composants non utilises, contredire la priorisation auth-first.
- Modifier seulement si : changement reel de stack, nouvelle contrainte technique, ou precision necessaire sur l'architecture.
- Tests associes : verification d'alignement entre `stacktechnique.md`, les dependances installees et la structure du code.
