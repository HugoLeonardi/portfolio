# CLAUDE.md — Règles de présentation du Portfolio

Ce fichier définit les règles de présentation à respecter sur **tout** le portfolio.
Toute modification de la présentation doit être répercutée ici.

---

## Identité visuelle

- **Nom affiché dans le logo** : `Hugo Léonardi` (sur toutes les pages, sans exception)
- **Titre du portfolio** : `Portfolio BTS SIO SISR`
- **Format des balises `<title>`** : `[Nom de la page] - Portfolio BTS SIO SISR`
  - Ex : `Mon CV - Portfolio BTS SIO SISR`, `Mes Missions - Portfolio BTS SIO SISR`
  - Exception : la page d'accueil → `Portfolio - BTS SIO SISR`
- **Footer** : `© 2025 - Hugo Léonardi - Portfolio BTS SIO SISR` (identique sur toutes les pages)

---

## Philosophie esthétique

Le design est **clair, épuré et lisible** — conçu pour une présentation orale.

- Fond général **blanc** (`#ffffff`), sections claires en `#f8fafc`
- **Aucun dégradé** — tous les fonds sont blancs ou gris très clair ; les accents bleus passent par des bordures et des badges
- Ombres légères et subtiles uniquement sur les cartes principales
- Le bleu (`#2563eb`) est l'accent dominant : boutons primaires, badges, bordures actives, texte des liens
- Textes principaux en `#1e293b` (quasi-noir), textes secondaires en `#64748b` (gris moyen)
- **Aucun texte blanc sur fond coloré** sauf dans les badges et boutons primaires

---

## Navigation

La barre de navigation est identique sur toutes les pages. Ordre des liens :

1. `Accueil` → `index.html`
2. `Technicentre de Villeneuve Saint Georges` → `entreprise.html`
3. `CV` → `cv.html`
4. `Projets` → `projets.html`
5. `Missions` → `missions.html`
6. `Veille` → `veille.html`

Les liens de navigation sont en gris (`--text-light`) avec `padding: 0.4rem 0.85rem` et `border-radius: 6px`. Au survol : fond `--bg-light`. Le lien de la page courante porte la classe `class="active"` : fond `#eff6ff`, texte bleu, font-weight 600.

---

## Palette de couleurs (variables CSS)

Définie dans `style.css`, à ne pas modifier sans mettre à jour ce fichier.

| Variable              | Valeur     | Usage                                      |
|-----------------------|------------|--------------------------------------------|
| `--primary-color`     | `#2563eb`  | Boutons primaires, liens actifs, accents   |
| `--primary-dark`      | `#1e40af`  | Hover boutons primaires                    |
| `--secondary-color`   | `#64748b`  | Texte secondaire                           |
| `--accent-color`      | `#0ea5e9`  | Accents secondaires (phase-number, etc.)   |
| `--text-dark`         | `#1e293b`  | Texte principal                            |
| `--text-light`        | `#64748b`  | Texte secondaire / descriptions            |
| `--bg-light`          | `#f8fafc`  | Fond sections, cartes internes             |
| `--bg-white`          | `#ffffff`  | Fond général, cartes principales           |
| `--border-color`      | `#e2e8f0`  | Bordures                                   |
| `--success-color`     | `#10b981`  | Éléments validés / complétés              |

---

## Typographie

- **Police** : `'Segoe UI', Tahoma, Geneva, Verdana, sans-serif`
- **Interligne** : `1.6` (corps), `1.8` (blocs de texte)
- **Tailles de titres** :
  - `h1` hero : `3rem`, font-weight 800, letter-spacing `-0.03em`
  - `h1` page-header : `2rem`, font-weight 800
  - `h2` : `1.5rem`, font-weight 700
  - `h3` : `1.15rem`, font-weight 600
  - `h4` : `1rem`, font-weight 600

---

## Règles d'usage des emojis

| Niveau         | Emoji autorisé ? | Remarque                                              |
|----------------|------------------|-------------------------------------------------------|
| `<h1>`         | ❌ Non           | Jamais d'emoji dans les titres de page-header         |
| `<h2>`         | ❌ Non           | Titres de section propres, sans emoji                 |
| `<h3>`         | ✅ Oui           | Emojis acceptés pour les catégories (missions, etc.)  |
| `<h4>` et +    | ✅ Oui           | Emojis acceptés                                       |
| `info-box`     | ✅ Oui           | Emojis acceptés dans les blocs info                   |
| `feature-card` | ✅ Oui           | Emojis dans les icônes de cartes                      |

---

## Structure des pages

### Page d'accueil (`index.html`)
- Section hero **fond blanc** avec badge `BTS SIO SISR` (pilule bleue claire)
- `<h1>` sombre avec `<span>` bleu pour le mot "Portfolio"
- Grille de 4 feature-cards de navigation rapide (fond blanc, bordure fine)
- Deux boutons CTA : `Mon CV` (btn-primary = bleu plein) + `Mes Projets` (btn-secondary = contour bleu)
- Section features sur fond `#f9fafb`

### Pages internes (toutes sauf index)
- `<section class="page-header">` : fond clair (`#f9fafb`), **bordure bleue en haut** (3px), **pas de gradient**
  - `<h1>` : titre de la page, **sans emoji**, texte sombre
  - `<p>` : sous-titre descriptif court, texte gris
- `<section class="content-section">` pour le contenu
- Contenu organisé en `<div class="content-card">` (fond blanc, bordure fine, ombre légère)

### Pages de détail projet (`projet1.html`, `projet2.html`)
- Fil d'Ariane (`breadcrumb`) → lien retour vers `projets.html`
- `<section class="project-detail-header">` : même style que `page-header` (fond clair + bordure bleue top)
  - Badge projet (pilule `#eff6ff`), `h1` sombre, sous-titre gris, bouton PDF (btn-primary bleu)
- `<section class="project-detail-content">` pour le contenu

---

## Composants réutilisables

### Boutons
- `.btn.btn-primary` : fond bleu (`#2563eb`), texte blanc — CTA principal
- `.btn.btn-secondary` : fond blanc, bordure bleue, texte bleu — CTA secondaire (sur fond clair)
- `.btn.btn-full` : pleine largeur (dans les cartes de projet)
- `.btn-compte-rendu` : petit bouton bleu clair (missions), non-`btn`

### Tags technologiques
- `.tag` : badge bleu clair (`#eff6ff`, texte `#2563eb`, bordure `#bfdbfe`) — taille normale
- `.tag-small` : même style, plus petit — pour les missions/projets

### Cartes de mission (`.mission-item`)
- Fond clair (`--bg-light`), bordure bleue gauche 3px
- Structure : `h4` titre, `<p><strong>Contexte/Objectifs</strong></p>`, `<ul>`, `.mission-tags`, `.btn-compte-rendu`

### Timeline CV (`.timeline-item`)
- Grille 2 colonnes : date (`140px`) + contenu (`1fr`)
- Date en `--primary-color`

### Theme cards (veille)
- Fond blanc, bordure fine, **bordure gauche bleue 3px** (remplace l'ancien gradient violet)

### Conclusion veille
- Fond bleu très clair (`#eff6ff`) à la place de l'ancien gradient violet

### Infra cards (entreprise)
- Fond blanc, bordure top bleue 3px (remplace l'ancien fond bleu foncé)

---

## Fichiers

| Fichier              | Rôle                                      |
|----------------------|-------------------------------------------|
| `index.html`         | Accueil                                   |
| `cv.html`            | Curriculum Vitae                          |
| `entreprise.html`    | Présentation SNCF Voyageurs / Technicentre|
| `missions.html`      | Missions entreprise et école (onglets)    |
| `projets.html`       | Liste des projets BTS                     |
| `projet1.html`       | Détail Projet 1 (Nextcloud/AWS)           |
| `projet2.html`       | Détail Projet 2 (VLAN Cisco)              |
| `veille.html`        | Veille technologique DevOps               |
| `style.css`          | Feuille de style unique                   |
| `index-preview.html` | Preview standalone (peut être supprimé)   |
| `docs/`              | PDFs des comptes-rendus et fiches missions|
| `images/`            | Photos et schémas                         |
