# Zone d'attente

Application web pour l'éducation physique, pensée pour un tableau interactif.
Pendant un jeu de prise du drapeau, les élèves touchés par une balle vont en zone d'attente
et appuient sur leur prénom. Leur bouton passe du rouge au vert : quand il est entièrement vert, ils peuvent revenir en jeu.

## Fonctions

- Deux équipes affichées côte à côte, avec leur nom et leur liste d'élèves.
- Un chrono d'attente par élève (de 30 s à 3 min, ou une durée au choix), avec une balle qui rebondit et des messages rigolos.
- Le bouton clignote en vert pendant 5 secondes, puis redevient blanc tout seul.
- Un temps de jeu total, avec Pause, Reprendre et Terminer. La pause arrête aussi les chronos d'attente.
- Un palmarès à la fin : les moins touchés (« Les Intouchables ») avec un feu d'artifice, les plus touchés (« Les Téméraires ») avec une pluie de balles, et le bilan des équipes.
- Les listes d'élèves se collent ou s'importent depuis un fichier `.txt` ou `.csv`.
- L'application fonctionne sans internet une fois installée.
- Les réglages, les listes et la partie en cours sont enregistrés sur l'appareil.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète |
| `manifest.webmanifest` | Nom, icône et couleurs de l'application installée |
| `sw.js` | Permet le fonctionnement hors connexion |
| `icons/` | Icônes de l'application |
| `.nojekyll` | Indique à GitHub Pages de publier les fichiers tels quels |

## 1. Mettre l'application sur GitHub

1. Créez un compte sur [github.com](https://github.com) si vous n'en avez pas.
2. Cliquez sur **New repository**, nommez-le par exemple `zone-attente`, cochez **Public**, puis **Create repository**.
3. Sur la page du dépôt, cliquez sur **uploading an existing file**.
4. Glissez **tout le contenu** du dossier `zone-attente` : les fichiers et le dossier `icons`.
   Le fichier `.nojekyll` est caché sur Mac et Windows. S'il n'apparaît pas, ce n'est pas grave.
5. Cliquez sur **Commit changes**.

## 2. Publier le site (GitHub Pages)

1. Dans le dépôt, ouvrez **Settings**, puis **Pages** dans le menu de gauche.
2. Sous **Build and deployment** › **Source**, choisissez **Deploy from a branch**.
3. Choisissez la branche **main** et le dossier **/ (root)**, puis cliquez sur **Save**.
4. Attendez 1 à 2 minutes. L'adresse s'affiche en haut de la page, par exemple :
   `https://votre-nom.github.io/zone-attente/`

## 3. Installer l'application sur le bureau du tableau interactif

Le tableau doit utiliser **Chrome** ou **Edge**.

1. Ouvrez l'adresse GitHub Pages sur le tableau.
2. Cliquez sur le bouton **Installer l'application** en haut à droite de l'écran.
   Vous pouvez aussi cliquer sur l'icône d'installation à droite de la barre d'adresse.
   Dans Edge, vous la trouvez aussi dans le menu **…** › **Applications** › **Installer ce site en tant qu'application**.
3. Une icône **Zone d'attente** est créée sur le bureau et dans le menu Démarrer. L'application s'ouvre dans sa propre fenêtre, sans barre d'adresse.

Une fois installée, l'application fonctionne même si le tableau n'est plus connecté à internet.
Le bouton **Plein écran** reste disponible pour occuper tout le tableau.

### Sans internet ni GitHub

Vous pouvez aussi copier le fichier `index.html` sur le tableau (avec une clé USB, par exemple) et l'ouvrir d'un double-clic.
Tout fonctionne, sauf l'installation sous forme d'application. Les polices de caractères seront remplacées par des polices
du système si le tableau n'a pas internet.

## Mettre à jour l'application

1. Remplacez `index.html` sur GitHub : **Add file** › **Upload files**.
2. Dans `sw.js`, augmentez le numéro de version (`zone-attente-v1` devient `zone-attente-v2`).
3. Sur le tableau, ouvrez l'application connectée à internet. La nouvelle version se charge, parfois après une deuxième ouverture.

## Bon à savoir

- Les listes d'élèves et les parties sont enregistrées **uniquement sur l'appareil** où l'application est utilisée.
  Elles ne sont jamais envoyées sur internet.
- Si vous videz les données du navigateur, vous devrez saisir de nouveau les listes d'élèves.
- Pour modifier les phrases d'attente ou les titres du palmarès, cherchez `const MSG`, `const LEAST` et `const MOST` dans `index.html`.

## Licence

MIT. Vous pouvez librement utiliser, modifier et partager l'application.
