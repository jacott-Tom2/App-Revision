# App Révision

## Présentation

**App Révision** est une application d’apprentissage et de révision pour les élèves. Elle leur permet d’importer leurs leçons, de les étudier et de mesurer leurs progrès.

L’application s’ouvre avec un lien dans le navigateur sur iPhone, iPad et ordinateur. Aucune installation n’est nécessaire. L’interface doit s’adapter à la taille de l’écran et rester simple à utiliser sur téléphone et tablette.

## Objectifs du projet

- Organiser les leçons dans plusieurs matières et branches scolaires.
- Transformer une leçon photographiée ou importée en contenu utile pour apprendre et réviser.
- Proposer un parcours adapté au niveau de l’élève.
- Montrer les progrès réalisés pour chaque leçon et aider l’élève à choisir quoi revoir ensuite.

## Parcours utilisateur

1. L’élève ouvre l’application à partir d’un lien.
2. Il crée son compte ou se connecte avec un nom d’utilisateur et un mot de passe.
3. Il choisit une matière, puis une leçon existante ou en ajoute une nouvelle.
4. Il photographie la leçon avec l’appareil de son téléphone ou de sa tablette, ou choisit un fichier à importer.
5. Il vérifie le contenu reconnu et peut le corriger si nécessaire.
6. Il choisit le mode **Apprendre** ou **Réviser**.
7. À la fin de la séance, il consulte son résultat, ses progrès et les points à retenir.

## Fonctionnalités

### Compte et matières

- Création de compte et connexion avec un nom d’utilisateur et un mot de passe.
- Retrouver ses matières, ses leçons et son historique après connexion.
- Organisation des cours par matière, branche et leçon, par exemple : sciences → biologie → cellules.

Les mots de passe devront être stockés de manière sécurisée et jamais conservés en clair.

### Ajout d’une leçon

- Prendre une photo directement depuis l’appareil photo, lorsque le navigateur le permet.
- Choisir une photo ou un document déjà présent sur l’appareil.
- Accepter au minimum les photos et les PDF ; les autres formats pourront être ajoutés ensuite.
- Extraire le texte de la leçon et permettre à l’élève de le vérifier et de le corriger.
- Garder un lien entre les exercices créés et la leçon d’origine pour retrouver la source.

### Apprentissage et révision

**Apprendre** propose des explications, des exemples et des questions progressives, avec des indices lorsque l’élève en a besoin.

**Réviser** propose des questions et des exercices pour vérifier ce que l’élève sait déjà. Les réponses sont corrigées et les notions difficiles sont proposées à nouveau lors de séances ultérieures.

### Objectif de réussite

- L’objectif par défaut est **80 % de réussite** pour chaque leçon.
- L’élève peut modifier cet objectif.
- Le bilan indique si l’objectif est atteint et les notions qui restent à travailler.
- Les réponses données avec un indice peuvent être distinguées des réponses réussies sans aide.

### Statistiques et bilan par leçon

Après chaque séance, afficher :

- le temps passé dans la séance et le temps cumulé sur la leçon ;
- le nombre de questions et de réponses ;
- les bonnes réponses, les erreurs et, si possible, les réponses données avec une aide ;
- la progression des notions travaillées et maîtrisées ;
- l’évolution des résultats au fil des séances ;
- les prochaines notions à réviser ;
- un **« À retenir »** (*takeaway*) avec les idées essentielles de la leçon.

Les résultats devraient rester lisibles dans le temps : par exemple, comparer les dernières séances et préciser si le pourcentage est calculé sur les réponses faites avec ou sans aide.

## Première version (MVP)

La première version doit permettre de réaliser le parcours de bout en bout :

1. Ouvrir l’application dans un navigateur, sur téléphone, tablette ou ordinateur.
2. Créer un compte et se connecter.
3. Créer ou choisir une matière et une leçon.
4. Importer un PDF ou une photo, ou prendre une photo depuis l’appareil.
5. Vérifier le texte reconnu.
6. Générer ou préparer une fiche, des questions et un quiz à partir de la leçon.
7. Utiliser les modes Apprendre et Réviser.
8. Enregistrer les séances et afficher le bilan avec l’objectif par défaut de 80 %.

## Pistes d’évolution

- Révisions espacées et calendrier des prochaines séances.
- Plan de révision en fonction d’une date de contrôle.
- Difficulté des exercices adaptée aux réponses précédentes.
- Diagnostic initial pour repérer les notions acquises et celles à travailler.
- Partage de cours ou espace enseignant, après validation des usages individuels.
- Export ou impression des fiches de révision.

## Principes d’expérience

- Interface claire, en français et adaptée aux petits écrans.
- Séances courtes et faciles à reprendre.
- Contenu généré vérifiable et modifiable par l’élève.
- Indication claire lorsque la photo est floue ou que le texte a été mal reconnu.
- Contrôle par l’utilisateur de ses documents et de leur suppression.

## Alarme de quota Codex / Pi

L’environnement de développement Pi peut surveiller le quota Codex depuis l’endpoint d’usage ChatGPT :

`https://chatgpt.com/backend-api/wham/usage`

L’alarme est configurée pour se déclencher à **50 % de quota utilisé**, avec une vérification toutes les **5 minutes**. Elle surveille les fenêtres de quota de 5 heures et hebdomadaire, puis affiche une notification Pi lorsque le seuil est franchi.

### Commandes Pi

```text
/codex alarm status
/codex alarm 50 5
/codex alarm off
```

La configuration est stockée localement dans `~/.pi/agent/codex-accounts.json` et ne doit jamais être commitée, car l’authentification OAuth reste privée. L’alarme nécessite une session Pi ouverte et un compte `openai-codex` authentifié. Après installation ou modification, redémarrer Pi pour charger l’extension.

## Documentation GitHub

Ce README sert de référence produit initiale. La suite du projet pourra documenter les tâches dans les *Issues*, les étapes dans une *Roadmap*, puis les choix techniques dans un document d’architecture dédié.
