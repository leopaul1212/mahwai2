# Fonctionnalites du projet (MVP)

## Objectif

Documenter les fonctionnalites metier du SaaS Aide Devoirs pour aligner produit, conception et implementation.

## Fonctionnalites coeur MVP

1. Authentification et gestion des roles
   - Connexion securisee avec Auth.js (NextAuth).
   - Attribution et controle des roles `PARENT` et `ENFANT`.
   - Protection des pages et APIs selon le role.

2. Creation/saisie d'un devoir
   - Saisie manuelle du devoir (MVP) via formulaire.
   - Import simple de contenu de devoir (texte) en entree du pipeline.

3. Guidance pedagogique par `IA_TUTEUR`
   - Transformation du devoir en plan d'action clair, etape par etape.
   - Consignes adaptees a l'enfant pour realiser le travail.

4. Soumission de la reponse par l'enfant
   - Envoi d'une reponse texte.
   - Ajout optionnel d'une photo de copie (`/public/uploads` en MVP).

5. Correction automatique par `IA_CORRECTEUR`
   - Evaluation de la reponse avec score.
   - Explication des erreurs et des points a corriger.

6. Recommandation de suite par `IA_COACH`
   - Proposition d'action selon la performance (continuer, refaire, renforcer un point).

7. Espace parent de validation
   - Visualisation du score, du temps et de la progression.
   - Decision pedagogique finale : continuer, refaire, ou notifier.

8. Historique minimal des devoirs
   - Stockage des soumissions et resultats (PostgreSQL/Prisma).
   - Consultation de l'historique recent pour suivi.

## Fonctionnalites prevues apres stabilisation MVP

- Connecteurs ENT/Pronote pour recuperation automatique des devoirs.
- Monitoring avance (ex: Sentry) et tests E2E systematiques.
- Stockage cloud des fichiers (S3/R2) avec URLs securisees.

## Critere de reussite MVP

Le projet est considere fonctionnel quand un flux complet peut etre execute :
`connexion -> saisie devoir -> guidance IA -> soumission enfant -> correction IA -> decision parent`.
