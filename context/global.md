# Global projet - SaaS Aide Devoirs (MVP)

## Vision

Construire un SaaS qui aide les enfants a faire leurs devoirs avec un accompagnement IA guide, puis donne aux parents une vue claire pour decider de continuer ou refaire.

## Probleme resolu

- Les devoirs sont souvent peu structures, avec peu de feedback immediat.
- Les parents manquent de visibilite sur la qualite reelle du travail.
- Les corrections arrivent tard et ne permettent pas toujours une boucle d'amelioration rapide.

## Utilisateurs cibles

- Enfant : suit un parcours guide et remet une preuve de travail (texte + photo).
- Parent : consulte score, temps, progression et prend une decision pedagogique.

## Flux metier MVP

1. Le devoir est saisi (mock/import manuel au debut).
2. `IA_TUTEUR` transforme le devoir en plan d'action clair.
3. L'enfant suit les etapes et soumet sa reponse.
4. `IA_CORRECTEUR` evalue, note et explique les erreurs.
5. Le parent valide la suite : continuer, refaire, ou notifier.

## Priorites produit actuelles

1. Authentification + roles `PARENT | ENFANT`
2. Pipeline IA (tuteur -> correction)
3. Stockage des soumissions et des scores
4. Interfaces enfant/parent minimales
5. Connecteurs ED/Pronote apres stabilisation MVP

## Stack retenue (reference)

- Front/Back : Next.js (App Router + API Routes/Server Actions)
- UI : Tailwind CSS + shadcn/ui
- Data : PostgreSQL + Prisma
- Auth : Auth.js (NextAuth)
- IA : OpenAI API (appels serveur uniquement)

Voir `context/stacktechnique.md` pour le detail technique complet.

## Etat actuel du projet

- Le projet est au stade documentation/cadrage MVP.
- La roadmap detaillee est suivie dans `context/avancement.md`.
- Les decisions majeures sont historisees dans `context/contexte.md`.
- Les actions realisees sont journalisees dans `context/tâcheaccomplie.md`.

## Objectif court terme

Livrer un premier parcours fonctionnel de bout en bout, securise par role, avec un flux IA testable en conditions reelles (devoir -> guidance -> soumission -> correction -> decision parent).
