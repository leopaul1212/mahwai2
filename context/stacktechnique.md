# Stack technique du projet (MVP)

## Vision generale

Ce projet est un SaaS d'aide aux devoirs avec un pipeline IA. Le choix de stack privilegie la simplicite de mise en place, la rapidite d'iteration, et la securite des appels IA cote serveur.

## Frontend

- Next.js (App Router)
  - Role : interface enfant/parent + rendu des pages.
  - Pourquoi : front et back dans le meme projet, bonne integration avec auth et API.
- Tailwind CSS
  - Role : styling rapide et maintenable.
- shadcn/ui
  - Role : composants UI solides et reutilisables.
- react-hook-form + zod
  - Role : gestion de formulaires + validation stricte des donnees.

## Backend

- Next.js API Routes / Server Actions
  - Role : endpoints metier (auth, devoirs, uploads, pipeline IA).
  - Pourquoi : evite un backend separe, centralise la logique serveur.

## Base de donnees

- PostgreSQL
  - Role : stockage relationnel (users, devoirs, soumissions, scores, interactions IA).
- Prisma ORM
  - Role : acces DB type-safe + migrations.

## Authentification

- Auth.js (NextAuth)
  - Role : login, session, controle d'acces.
  - Strategie MVP : email/mot de passe + roles `PARENT | ENFANT`.

## IA

- OpenAI API (texte + vision)
  - Role : generation de parcours pedagogiques, correction, coaching.
  - Regles : appels uniquement cote serveur, sorties JSON strictes, prompts versionnes.
- Roles IA internes
  - `IA_TUTEUR` : transforme un devoir brut en plan d'action.
  - `IA_CORRECTEUR` : note et explique les erreurs.
  - `IA_COACH` : propose la suite selon le score.

## Upload et stockage fichiers

- MVP : stockage local (`/public/uploads`) pour les photos de devoirs.
- Evolution : S3 ou Cloudflare R2 avec URLs securisees.

## Securite

- Validation Zod sur les entrees/sorties critiques.
- Verification des roles dans les routes et actions serveur.
- Chiffrement des donnees sensibles (credentials ED/Pronote quand ajoutes).

## Monitoring et tests

- MVP : logs applicatifs simples + logs Prisma.
- Plus tard : Sentry pour le suivi d'erreurs.
- Strategie tests : validation manuelle au debut, puis E2E Playwright.

## Architecture cible (reference)

```txt
/app
 ├── (auth)
 ├── (child)
 ├── (parent)
 ├── api
 │    ├── ai
 │    ├── homework
 │    └── upload
 └── layout.tsx

/prisma
 └── schema.prisma

/lib
 ├── ai
 │    ├── tutor.ts
 │    ├── corrector.ts
 │    └── prompts
 ├── auth.ts
 └── db.ts

/components
/hooks
```

## Regle de priorisation actuelle

1. Auth + roles
2. Pipeline IA
3. Stockage reponses + scores
4. Interfaces enfant/parent
5. Connecteurs ED/Pronote
