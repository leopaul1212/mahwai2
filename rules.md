Voici les règles que tu dois absoluments suivre quand tu codes une nouvelle features. 
1-Je dois comprendre le code à la fin et me l'approprier même si je n'ai pas un niveaux tecknique très élévé voici les pratique:

    a-au début de chaque fichier tu dois mettre un commentaire qui explique à quoi sert se fichier, qui explique sa position dans le workflow d'un feature (qu'elle sont les entrés du code, qu'elle sont les sortie) et les structure globale du fichier (un arbre de désition qui part de l'input vers l'output et qui décris la logique). garde bien en tête que cela dois être concis mais garder tout les informations nécessaire.


#### Template — En-tête de fichier (copier/coller)
*(adapte juste le style de commentaire à ton langage : `//` JS/TS, `#` Python, `/* */` etc.)*
```txt
[FILE] <NomDuFichier> — <Rôle en 1 phrase>
Workflow: <où ce fichier s’insère / qui l’appelle / pourquoi>
Inputs: <liste courte>
Outputs: <liste courte>
Decision tree:
- Input -> <étape 1>
  - if <condition A> -> <résultat A>
  - else -> <résultat B>
- -> <étape finale / output>
Structure: <liste des blocs/sections du fichier, dans l’ordre>




    b-tu dois diviser dans chaque fichier le code en bloc de code (de façon à ce que chaque bloque et un output et un input), applique la règle a- pour chaque bloque de code (de façon plus courte (1-2 ligne max)). Un bloc de code correspond à une case dans l'abre de désision de la règle a- .

Template — Commentaire de bloc
[BLOC] <Nom du bloc> — Input: <...> -> Output: <...>
But: <à quoi sert ce bloc en 1 phrase>



2-Va au plus simple et n'écris pas de code inutiles:
    a-Lorsque tu dois écrire du code tu dois être sur qu'il est absolument nécessaire pour cela regarde le projet pour voir si tu n'as pas écrit une fonction/bou de code similaire à réutiliser. Chaque ligne dois être nécessaire (et dois répondre à la feature demander).
    b-Lorsque tu dois écrire du code demande toi avant si une suppression/modification ne fais pas la même chose si oui fais ça à la place
    c- Pas de code verbeux, pas de complexité inutile, pas d’abstraction décorative. Code court, clair, utile, maintenable — point final.

3- règle pour ne pas casser le projet:  
Avant ne modifier, ajouter, supprimer du code tu dois te demander si ça ne casse aucun autre workflow/feature ton but n'est pas de brouiller le projet mais de l'améliorer: pour cela à chaque fois cherche qu'elle autre bou de code dépens du code que tu vas écrire et réflechie à la logique pour avoir que ce bou de code dépendant reçoive le bonne input du code que tu vas écrire. 

4 contexte: Tu dois toujours écrire du codes contextualisé pour cela observe constamment le projet afin que ton code sois le plus qualitatif possible. Parallèment à chaque fois que tu as modifier le projet tu dois mettre à jour les fichiers de contexte planprojet.md, avancement.md, tâcheaccomplie.md, contexte.md, rulesIA.md de la façon suivante: 


planprojet.md : C'est un fichier qui donne un apperçu global du projet sous forme d'arbre, lorsque tu rajoute un fichier tu rajoutes une branche à l'arbre avec son nom et ce qu'il fait (input/output)

Template — Entrée planprojet.md
- <Dossier ou Feature>
  - <NomDuFichier.ext> : <rôle court>
    - Inputs : <...>
    - Outputs : <...>


avancemen.md: C'est un fichier qui regroupe toute les features à implémenter dans le projet avec des cases à cocher, quand tu as implémenter la features dans la case tu mets "à tester" en rouge avec derrière les choses à tester entre parenthèse, si tu as implémenter un feature qui n'était pas dans le fichier rajoute là de la même façon et cohérente par rapport à l'organisation. 

Template — Feature dans avancement.md
- [ ] <Nom de la feature> — <desc courte>
  - Statut : <span style="color:red">à tester</span> (tests: <liste courte>)


tâcheaccomplie.md: ce document regroupe une liste de tout ce qui à était accomplie/modifier dans le projet, à chaque fois tu rajoutes une ligne avec:
    -titre de l'action 
    -but de l'action 
    -une brève description de ce que tu as fait 
    -les fichiers modifier 
    -ce qu'il faut tester et ce que tu as tester

Template — Entrée tâcheaccomplie.md
- **[YYYY-MM-DD] Titre**  
  - But : <objectif>
  - Description : <ce qui a été fait, bref>
  - Fichiers modifiés : <liste>
  - Tests : <ce que tu as testé> / À tester : <ce qui reste>



contexte.md: ce fichier est destiné à être lu par les IA afin de faire un présentaton globale du projet et ce qui à était accomplie, c'est un gros fichier texte que tu dois mettre à jour à chaque fois que tu le juge nécessaire. 

Template — Entrée contexte.md
## [YYYY-MM-DD] <Changement / Feature>
- Contexte : <pourquoi>
- Résumé : <quoi>
- Impact : <workflows touchés>
- À tester : <liste>



rulesIA.md: à chaque fois que tu rajoutes du code tu dois mettre à jour ce fichier pour décrire aux autres IA comment il se comporte (ce qu'il ne faut pas faire, comme intérragire avec le code, à quoi il sert), tu dois bien sur rajouter le fichier et les lignes pour le situer. 

Template — Entrée rulesIA.md
### <NomDuFichier.ext>
- Rôle : <1 phrase>
- Contrat Input/Output : Inputs <...> -> Outputs <...>
- Ne pas faire : <liste courte des pièges / interdits>
- Modifier seulement si : <conditions>
- Tests associés : <liste>