# Résumé des changements — Site vitrine DO Stats Tracker

**Fichier modifié :** `landing/index.html`  
**Déploiement :** upload manuel sur Netlify (do-stats-tracker.netlify.app)

---

## 1. Texte de présentation + comparatif Free/Pro

### Hero
- **Accroche :** « Vos stats DarkOrbit, enfin sous contrôle. » (FR) / « Your DarkOrbit stats, finally under control. » (EN)
- **Sous-texte :** Présentation des 5 piliers (classements live, événements, comparaison, alertes) et ton orienté gaming / professionnel.

### Fonctionnalités (5)
- **Hall of Fame (classements)** — Scraping 24 serveurs (Honneur, XP, Top User, Aliens, Vaisseaux).
- **Profils & suivi joueurs** — Stats pilotes (grade, kills, portes) et évolution.
- **Comparaison entre joueurs** — Comparaison côte à côte et tendances.
- **Sidebar événements** — Événements en cours/à venir avec timers.
- **Notifications** — Alertes booster, fin de collecte, rappels (selon offre).

### Tableau Free vs PRO
- Section **« Free vs PRO »** avec tableau : Serveurs (restreints / 24), Scraping (limité / illimité), Profils (limité / complet), Comparaison (basique / complet), Événements (oui/oui), Support (communauté / prioritaire).
- Style aligné au reste du site (bordures, couleurs accent, fond sombre).

---

## 2. Onglet Changelog

- **Navigation :** lien « Changelog » dans le header (ancrage `#changelog`).
- **Section Changelog** avec titre + courte intro.
- **Structure par entrée :** version (ex. `v2.1.0`) + date (ex. `Mars 2026`) + liste à puces.
- **Première entrée fictive v2.1.0 — Mars 2026 :**
  - Mise à jour HoF 24 serveurs
  - Sidebar événements (timers, descriptions)
  - Comparaison joueurs (export, lisibilité)
  - Notifications Windows optionnelles
  - Corrections et perfs
- **Mise à jour manuelle :** dans le code, le changelog est un tableau JavaScript `entries` ; ajouter un objet `{ version, date, changes: [] }` pour une nouvelle entrée.

---

## 3. Placeholders pour screenshots

- **Hero :** une zone « Dashboard » (placeholder texte « Dashboard — screenshot à venir »).
- **Section « Aperçu de l’application »** avec 4 zones en grille 2×2 :
  - Dashboard (principal)
  - Hall of Fame / Classements
  - Comparaison entre joueurs
  - Sidebar événements
- Chaque zone contient :
  - Une **balise `<img>`** avec `class="screenshot-img w-full h-full object-cover"` et `alt` descriptif.
  - Un **placeholder visuel** (fond dégradé + texte) affiché tant qu’aucun `src` n’est renseigné.
- **Classes des zones :** `screenshot-zone screenshot-dashboard`, `screenshot-hof`, `screenshot-comparaison`, `screenshot-sidebar` pour cibler facilement le remplacement par de vraies images (mettre l’URL en `src` sur l’`<img>` et masquer le texte placeholder si besoin).

---

## 4. Bouton télécharger

- **Lien :** `/downloads/DarkOrbitStatsTracker-Setup.exe` (constante `DOWNLOAD_PATH` en tête de script).
- **Attribut :** `download` sur tous les liens « Télécharger » (header, hero, section download).
- **Version affichée :** à côté du bouton dans la section download, ex. « Version **v2.1.0** » (constante `APP_VERSION`).
- **Mention plateforme :** sous le bouton : « Windows 10/11 — 64 bits » (FR) / « Windows 10/11 — 64-bit » (EN).

---

## Déploiement Netlify

1. Mettre à jour le fichier `landing/index.html` (et éventuellement `landing/` en racine du site ou sous-dossier selon la config Netlify).
2. Héberger l’exe à l’URL prévue : placer `DarkOrbitStatsTracker-Setup.exe` dans un dossier `downloads/` à la racine du site (ou configurer une redirection/route Netlify vers ce fichier).
3. Pour changer la version affichée ou le chemin d’exe : modifier en haut du script les constantes `APP_VERSION` et `DOWNLOAD_PATH`.

---

## Fichiers livrés

| Fichier | Description |
|---------|-------------|
| `landing/index.html` | Site vitrine complet (hero, 5 features, aperçu screenshots, tableau Free/Pro, changelog, download). |
| `landing/CHANGELOG_SITE.md` | Ce résumé des changements. |

Sidebar événements, tableau Free/Pro et contenu existant (couleurs, typo, ton) ont été conservés et intégrés dans le même style.
