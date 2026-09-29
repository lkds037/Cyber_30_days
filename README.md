# 🛡️ Cyber 30 Jours — Widget PWA

Widget de suivi pour le **parcours cybersécurité en 30 jours** (Linux → Réseaux → Fondamentaux → Hacking éthique), installable comme **application sur Android** depuis GitHub Pages, utilisable **100 % hors ligne**.

## 📂 Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète (widget + parcours + notes + sauvegarde) |
| `manifest.webmanifest` | Manifeste PWA (nom, icônes, mode plein écran) |
| `sw.js` | Service worker (fonctionnement hors ligne) |
| `icon-192.png` / `icon-512.png` | Icônes de l'app |
| `.nojekyll` | Désactive le traitement Jekyll de GitHub Pages (requis) |

## 🚀 Mise en ligne sur GitHub Pages (depuis Android)

### Méthode 1 — Application GitHub mobile (la plus simple)

1. Ouvre l'app **GitHub**, va dans **ton dépôt** (ou crée-en un nouveau, ex. `cyber30`).
2. Appuie sur **➕ → Upload files** (ou « Add file → Upload files » dans le navigateur).
3. Dépose **tous les fichiers** ci-dessus (index.html, manifest.webmanifest, sw.js, les 2 icônes, .nojekyll). Attention : les fichiers cachés comme `.nojekyll` ne se voient pas toujours dans la liste — c'est normal.
4. En bas, écris un message (ex. `Widget Cyber30J`) → **Commit changes** → branche `main`.
5. Va dans **Settings** (roue dentée) → **Pages** :
   - **Source** : `Deploy from a branch`
   - **Branch** : `main` / **(root)** → **Save**
6. Attends 1 à 3 minutes. Ton site est en ligne à l'adresse :
   `https://TON-PSEUDO.github.io/cyber30/`
   (visible aussi dans Settings → Pages, avec un badge vert ✅)

### Méthode 2 — Depuis le navigateur du téléphone

1. Sur `github.com`, ouvre ton dépôt → **Add file → Create new file** ou **Upload files**.
2. Pour `.nojekyll` : « Create new file », nomme-le exactement `.nojekyll`, laisse vide, commit.
3. Puis Settings → Pages → branche `main` / root → Save (comme ci-dessus).

> 💡 Sur PC, le plus rapide : glisse-dépose tous les fichiers sur la page du dépôt, ou utilise [github.dev](https://github.dev) (presse `.` depuis le dépôt) pour les éditer directement.

## 📲 Installer le widget sur ton écran d'accueil (Android)

1. Ouvre **Chrome** sur ton téléphone et va à l'URL de ton site GitHub Pages.
2. Menu **⋮** en haut à droite → **« Ajouter à l'écran d'accueil »** (ou « Installer l'application » si proposé).
3. Confirme → l'icône bouclier 🛡️ apparaît sur ton écran d'accueil, et l'app s'ouvre **en plein écran, sans barre d'adresse**.
4. Au premier lancement : choisis ta **date de début**, active les **🔔 rappels**, et importe le **📅 rappel .ics** dans ton agenda pour des notifications quotidiennes automatiques.

## 🔔 Les rappels, comment ça marche

Android n'autorise pas un site web à déclencher une notification chaque matin tout seul (il faudrait un serveur de push). Le widget propose donc deux solutions **sans serveur** :

1. **Rappel calendrier (.ics)** — recommandé : bouton « Télécharger le .ics (30 rappels) ». Ouvre le fichier téléchargé → ton app Agenda (Google Agenda, etc.) crée 30 événements, un par jour, avec **notification système à l'heure choisie** (par défaut 9 h 00, modifiable) + alarme 10 min avant.
2. **Rappel à l'ouverture** : si tu actives les notifications du site, l'app t'affiche le jour du jour à chaque ouverture/reprise — tant que le jour n'est pas validé.

## 🧰 Fonctionnalités

- **3 onglets** : Aujourd'hui · Parcours (30 jours cliquables) · Semaines (4 blocs colorés)
- Jour du jour **calculé automatiquement** depuis ta date de début (ou suit ton dernier jour validé)
- Théorie + **commandes terminal avec bouton Copier** + exercice + défi + validation pour chaque jour
- **Notes personnelles** par jour, **streak 🔥**, barre de progression
- **Sauvegarde/export** de ta progression en `.json` (pratique pour changer de téléphone)
- Tout est stocké **en local sur ton téléphone** (localStorage), rien n'est envoyé nulle part

## 🔄 Mettre à jour l'app

Si tu modifies un fichier : commit → GitHub Pages se met à jour en ~1 min. Le service worker (sw.js) sert d'abord la version en cache : ferme puis rouvre l'app, ou attends quelques minutes, pour voir la nouvelle version.

---

*Parcours d'origine : programme « 30 jours cybersécurité » (Linux Journey, Bandit, Professor Messer N10-008, TryHackMe Pre-Security & Complete Beginner).*
