## [2026-03-01] Plan de developpement MVP - SaaS Aide Devoirs
- Contexte : besoin de structurer le MVP autour du pipeline IA avant l'authentification et les connecteurs externes.
- Resume : creation d'un backlog detaille dans `context/avancement.md` avec priorites, ordre de dev et cas de test associes pour chaque feature.
- Impact : clarifie la sequence de travail pour les workflows ingestion devoir -> tutorat IA -> soumission enfant -> correction IA -> decision parent.
- A tester : mise en oeuvre des phases 0 a 8, en commencant par le pipeline IA sans auth.

## [2026-03-01] Changement de priorite - Auth en premier
- Contexte : decision produit de demarrer par la securisation des acces avant le pipeline IA.
- Resume : mise a jour de l'ordre de developpement dans `context/avancement.md` pour positionner `Auth + roles` en etape 1.
- Impact : les ecrans et endpoints MVP devront etre construits directement avec gestion de session et controle de role.
- A tester : login, gestion session, protection routes et APIs, liaison parent/enfant minimale.

## [2026-03-01] Ajout de la reference stack technique
- Contexte : besoin de disposer d'une source claire pour connaitre les technos retenues.
- Resume : creation du fichier `context/stacktechnique.md` avec description des outils et de leur role dans le MVP.
- Impact : facilite l'alignement produit/technique et evite les choix contradictoires pendant le developpement.
- A tester : coherence entre la stack documentee et les dependances/code reels lors des prochaines implementations.
