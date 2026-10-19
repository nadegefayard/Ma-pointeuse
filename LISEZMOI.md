# Ma pointeuse : mise en ligne

Compte environ 20 minutes la première fois. Tout est gratuit : Firebase (formule Spark) et GitHub Pages.

## Ce que contient le dossier

| Fichier | À quoi il sert |
|---|---|
| `index.html` | L'appli |
| `firebase-config.js` | Le lien vers TON projet Firebase (à remplir, étape 4) |
| `manifest.webmanifest`, `sw.js`, `icons/` | Ce qui rend l'appli installable et utilisable hors connexion |
| `firestore.rules` | Les règles de sécurité : chaque compte ne voit que ses propres heures |

## 1. Créer le projet Firebase

1. Va sur https://console.firebase.google.com et connecte-toi avec ton compte Google.
2. **Créer un projet**, nomme-le `pointeuse`. Tu peux désactiver Google Analytics, il ne sert à rien ici.

## 2. Activer la connexion par e-mail

1. Dans le menu de gauche : **Créer → Authentication → Commencer**.
2. Onglet **Mode de connexion** → **Adresse e-mail/Mot de passe** → active le premier interrupteur → **Enregistrer**.

## 3. Créer la base de données

1. Menu de gauche : **Créer → Firestore Database → Créer une base de données**.
2. Emplacement : choisis une région en Europe (par exemple `europe-west9 (Paris)`).
3. Choisis **Démarrer en mode production**, puis **Créer**.
4. Onglet **Règles** : efface tout, colle le contenu du fichier `firestore.rules`, puis **Publier**.

## 4. Relier l'appli à ton projet

1. Clique sur la roue ⚙️ en haut à gauche → **Paramètres du projet**.
2. En bas, section **Vos applications**, clique sur l'icône **Web** (`</>`), donne le nom `pointeuse`. Ne coche pas « Firebase Hosting ». Clique sur **Enregistrer l'application**.
3. Firebase affiche un bloc `const firebaseConfig = { apiKey: ..., ... }`.
4. Ouvre `firebase-config.js` avec un éditeur de texte (Bloc-notes, TextEdit en mode texte brut ou VS Code) et remplace les 6 valeurs par les tiennes. Enregistre.

> La clé `apiKey` n'est pas un mot de passe : c'est normal qu'elle soit visible dans l'appli. Ce sont les règles de l'étape 3 qui protègent tes données.

## 5. Mettre l'appli en ligne sur GitHub Pages

1. Sur https://github.com, **New repository**, nom : `pointeuse`, visibilité **Public**, puis **Create repository**.
2. Clique sur **uploading an existing file**, puis glisse **tout le contenu** du dossier (y compris le dossier `icons`). **Commit changes**.
3. Dans le dépôt : **Settings → Pages** → Source : **Deploy from a branch**, Branch : `main` et `/ (root)` → **Save**.
4. Une à deux minutes plus tard, l'appli est en ligne à l'adresse : **https://nadegefayard.github.io/pointeuse/**

## 6. Autoriser cette adresse dans Firebase

**Authentication → Paramètres → Domaines autorisés → Ajouter un domaine** → `nadegefayard.github.io`.

## 7. Installer l'appli et créer ton compte

- **Sur ton ordi** (Chrome ou Edge) : ouvre l'adresse, puis clique sur l'icône « Installer » à droite de la barre d'adresse.
- **Sur iPhone** : ouvre l'adresse dans **Safari** → bouton Partager → **Sur l'écran d'accueil**.
- **Sur Android** : ouvre l'adresse dans Chrome → menu ⋮ → **Installer l'application**.

Sur le premier appareil, appuie sur **Créer un compte**. Sur les autres, connecte-toi avec le même e-mail et le même mot de passe : tes heures sont les mêmes partout.

## Modifier l'appli plus tard

Remplace le fichier sur GitHub, puis dans `sw.js` change `pointeuse-v1` en `pointeuse-v2` (puis v3, etc.). Sinon les appareils peuvent garder l'ancienne version. Ferme et rouvre l'appli pour voir la mise à jour.

## En cas de souci

- **« L'appli n'est pas encore reliée à Firebase »** : `firebase-config.js` n'est pas rempli, ou l'ancienne version est encore en ligne.
- **« Synchronisation interrompue »** : vérifie que les règles de l'étape 3 sont bien publiées.
- **Mot de passe oublié** : entre ton e-mail sur l'écran de connexion, puis appuie sur « Mot de passe oublié ». Regarde aussi dans tes spams.
