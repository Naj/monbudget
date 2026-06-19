# MonBudget — Application de gestion de budget familial

Application web de suivi de budget mensuel : revenus, dépenses par catégories, historique, graphiques, export Excel/PDF.

## 🚀 Déploiement Cloudflare Pages

### Option A — Connexion directe au repo GitHub (recommandé)

1. Pousse ce dossier sur un repo GitHub (voir étapes ci-dessous)
2. Sur [Cloudflare Pages](https://dash.cloudflare.com/?to=/:account/pages), clique **Créer un projet** → **Connecter à Git**
3. Sélectionne ton repo
4. Build settings :
   - **Framework preset** : `None`
   - **Build command** : *(laisser vide)*
   - **Build output directory** : `/`
5. Déployer

Chaque `git push` redéploiera automatiquement le site.

### Option B — Upload direct (sans GitHub)

Sur Cloudflare Pages → **Créer un projet** → **Upload assets** → glisser le dossier.

---

## 📦 Pousser ce dossier sur GitHub

```bash
cd MonBudget
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TON-USER/mon-budget.git
git push -u origin main
```

---

## 📱 PWA — Installation & hors-ligne

L'application est une **Progressive Web App** : elle peut être installée comme une vraie application (icône sur l'écran d'accueil/bureau, sans barre d'adresse) et fonctionne **hors-ligne** une fois chargée une première fois.

- **Sur mobile** (Android/iOS) : ouvrir le site → menu navigateur → "Ajouter à l'écran d'accueil" / "Installer l'application"
- **Sur desktop** (Chrome/Edge) : une icône d'installation apparaît dans la barre d'adresse

Comme l'app ne dépend d'aucune API externe, le mode hors-ligne est totalement fiable une fois le premier chargement effectué.

## 💾 Données et confidentialité

Toutes les données (revenus, dépenses, catégories) sont stockées **uniquement dans le navigateur** via `localStorage` — rien n'est envoyé à un serveur. Chaque appareil/navigateur a ses propres données.

**Important** : pensez à utiliser le bouton **💾 Sauvegarde** régulièrement dans l'application pour exporter vos données en JSON, en particulier avant de vider le cache du navigateur ou de changer d'appareil.

## 🗂️ Structure du projet

```
MonBudget/
├── index.html         ← Application complète (HTML/CSS/JS, fichier unique)
├── manifest.json       ← Manifeste PWA (nom, icônes, couleurs)
├── sw.js                ← Service worker (cache hors-ligne)
├── icon-192.png
├── icon-512.png
├── icon-maskable.png
├── _headers             ← En-têtes de sécurité Cloudflare Pages
└── README.md
```
