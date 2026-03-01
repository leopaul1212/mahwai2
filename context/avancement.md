# Plan de developpement MVP - SaaS Aide Devoirs

> Priorite decidee le 2026-03-01 : auth avant tout le reste.

- [ ] Initialiser le socle technique Next.js + Tailwind + shadcn + Prisma + PostgreSQL
  - Statut : <span style="color:red">a tester</span> (tests: demarrage app, connexion DB, migration Prisma)
- [ ] Mettre en place le modele de donnees MVP (User, Homework, IAInteraction, Submission, Score)
  - Statut : <span style="color:red">a tester</span> (tests: creation relations parent/enfant, creation devoir, creation soumission, creation score)
- [ ] Construire le pipeline IA (apres mise en place de l'auth)
  - Statut : <span style="color:red">a tester</span> (tests: devoir mock -> IA_TUTEUR -> stockage -> affichage enfant -> soumission -> IA_CORRECTEUR -> score)
- [ ] Creer l'ingestion des devoirs (mock/import manuel) avec normalisation des donnees
  - Statut : <span style="color:red">a tester</span> (tests: mapping coherent pour matiere/consigne/date/pieces jointes)
- [ ] Implementer IA_TUTEUR avec prompt versionne et sortie JSON stricte
  - Statut : <span style="color:red">a tester</span> (tests: validation Zod, stockage prompt+reponse+version, gestion erreurs JSON)
- [ ] Construire la restitution enfant guidee (pas de chat libre)
  - Statut : <span style="color:red">a tester</span> (tests: affichage "ce que tu dois faire", criteres, questions de comprehension)
- [ ] Implementer la preuve de travail enfant (texte + photo obligatoire)
  - Statut : <span style="color:red">a tester</span> (tests: upload photo, sauvegarde metadata heure/tentative, lecture fichier)
- [ ] Implementer IA_CORRECTEUR avec score, feedback et erreurs detectees
  - Statut : <span style="color:red">a tester</span> (tests: score sur 20 ou %, feedback pedagogique, statut reussite/echec)
- [ ] Ajouter la boucle d'amelioration (continuer/refaire/notifier parent)
  - Statut : <span style="color:red">a tester</span> (tests: seuil score, echec repete, proposition exercice cible)
- [ ] Creer interface enfant minimale (vue Aujourd'hui + progression)
  - Statut : <span style="color:red">a tester</span> (tests: affichage devoirs du jour, progression, retour feedback)
- [ ] Creer interface parent minimale (score, temps, decision continuer/refaire)
  - Statut : <span style="color:red">a tester</span> (tests: lecture performances enfant, action parent en cas d'echec)
- [ ] Ajouter l'authentification Auth.js et les roles PARENT|ENFANT
  - Statut : <span style="color:red">a tester</span> (tests: login, protection routes, verification role serveur)
- [ ] Preparer la gestion des credentials ED/Pronote chiffrees
  - Statut : <span style="color:red">a tester</span> (tests: chiffrement/dechiffrement, stockage securise)
- [ ] Integrer les connecteurs ED/Pronote via adaptateurs normalises (phase apres MVP)
  - Statut : <span style="color:red">a tester</span> (tests: import devoir depuis chaque source, compatibilite format interne)
- [ ] Renforcer securite et fiabilite (Zod partout, IA cote serveur, logs utiles)
  - Statut : <span style="color:red">a tester</span> (tests: refus payload invalide, absence fuite cle API, traces exploitables)
- [ ] Ajouter monitoring evolutif (MVP: logs; plus tard: Sentry)
  - Statut : <span style="color:red">a tester</span> (tests: suivi erreurs critiques, correlation appel IA/reponse)
- [ ] Planifier les tests E2E Playwright apres stabilisation MVP
  - Statut : <span style="color:red">a tester</span> (tests: scenario complet enfant+parent)
- [ ] Documenter la stack technique dans un fichier dedie
  - Statut : <span style="color:red">a tester</span> (tests: verification des choix front/back/db/auth/ia/securite)

## Ordre de dev recommande

- [ ] 1. Auth + roles
  - Statut : <span style="color:red">a tester</span> (tests: login, sessions, acces restreint par role)
- [ ] 2. Pipeline IA (apres auth)
  - Statut : <span style="color:red">a tester</span> (tests: flux complet de bout en bout)
- [ ] 3. Stockage reponses + scores
  - Statut : <span style="color:red">a tester</span> (tests: persistence et relecture des tentatives)
- [ ] 4. Interface enfant minimale
  - Statut : <span style="color:red">a tester</span> (tests: comprehension et execution guidee)
- [ ] 5. Interface parent minimale
  - Statut : <span style="color:red">a tester</span> (tests: decision parent fonctionnelle)
- [ ] 6. Connexion ED / Pronote
  - Statut : <span style="color:red">a tester</span> (tests: ingestion automatique stable)
- [ ] 7. Raffinage IA
  - Statut : <span style="color:red">a tester</span> (tests: qualite feedback, robustesse JSON)
- [ ] 8. Graphique & UX
  - Statut : <span style="color:red">a tester</span> (tests: lisibilite mobile/desktop)
