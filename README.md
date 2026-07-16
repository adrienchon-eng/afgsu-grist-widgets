# AFGSU Grist Widgets

> Widgets personnalises pour **AFGSU MANAGER** - Plateforme de gestion des formations AFGSU sur [Grist](https://grist.numerique.gouv.fr).

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-deployed-brightgreen)](https://adrienchon-eng.github.io/afgsu-grist-widgets/)
[![Grist](https://img.shields.io/badge/Grist-compatible-blue)](https://grist.numerique.gouv.fr)

---

## Widgets disponibles

### 1. Entonnoir Unite (`entonnoir.html`)

Widget de selection en cascade a 3 niveaux pour l'affectation d'unite d'un stagiaire.

**Cascade :** `Categorie` → `Sous-categorie` → `Unite`

**URL du widget :**
```
https://adrienchon-eng.github.io/afgsu-grist-widgets/entonnoir.html
```

**Colonnes requises dans Grist :**
| Colonne Grist | Type | Description |
|---|---|---|
| `Unite` | `Ref:Structures` | Reference vers la table Structures |
| `Categorie_Unite` | `Choice` (formule) | Calcule automatiquement depuis Unite |
| `Sous_Categorie_Unite` | `Ref:Ref_Sous_Categories` (formule) | Calcule automatiquement depuis Unite |

**Fonctionnement :**
1. Charge toutes les structures depuis la table `Structures`
2. L'utilisateur selectionne une **Categorie** → filtre les sous-categories
3. L'utilisateur selectionne une **Sous-categorie** → filtre les unites
4. L'utilisateur selectionne une **Unite** → ecrit l'ID de reference dans Grist
5. `Categorie_Unite` et `Sous_Categorie_Unite` se mettent a jour automatiquement via leurs formules

**Configuration dans Grist :**
1. Ajouter une vue "Widget personnalise"
2. Saisir l'URL ci-dessus
3. Niveau d'acces : **Acces complet au document**
4. Mapper la colonne `Unite` dans les parametres du widget

---

### 2. Index des fonctions (`index.html`)

Widget d'autocompletion pour les fonctions existantes dans le champ Categorie/Fonction.

**URL du widget :**
```
https://adrienchon-eng.github.io/afgsu-grist-widgets/index.html
```

---

## Architecture du depot

```
afgsu-grist-widgets/
├── entonnoir.html     # Widget entonnoir 3 niveaux (Categorie > Sous-cat > Unite)
├── index.html         # Widget autocompletion fonctions
└── README.md          # Ce fichier
```

## Technologies

- HTML/CSS/JS vanilla
- [Grist Plugin API](https://docs.getgrist.com/grist-plugin-api.js)
- Deploye via **GitHub Pages**

## Contexte

Ces widgets s'integrent dans **AFGSU MANAGER**, une application Grist pour la gestion des formations de premiers secours (AFGSU) dans les armees francaises. Le document principal est heberge sur [grist.numerique.gouv.fr](https://grist.numerique.gouv.fr).

## Auteur

[@adrienchon-eng](https://github.com/adrienchon-eng)
