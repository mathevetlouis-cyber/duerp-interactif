# DUERP Interactif v2.0

**Document Unique d'Évaluation des Risques Professionnels — Application web autonome**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![HAL](https://img.shields.io/badge/HAL-deposit-orange.svg)](https://hal.science)
[![Version](https://img.shields.io/badge/version-2.0-green.svg)]()

🔗 **Démo en ligne** : [https://www.referentdeontologue.fr/document-unique](https://www.referentdeontologue.fr/document-unique)

---

## Présentation

Application web monopage (single-page HTML) permettant aux collectivités territoriales et établissements publics de réaliser leur **Document Unique d'Évaluation des Risques Professionnels** (DUERP), conformément aux articles L. 4121-3 et R. 4121-1 du Code du travail.

L'outil intègre un double questionnaire :

- **30 questions sur les risques professionnels classiques**, réparties en 12 familles (TMS, chutes, manutention, chimique, biologique, bruit, électrique, thermique, écran, routier, incendie, machines) ;
- **20 questions sur les Risques Psychosociaux (RPS)**, structurées selon les 6 dimensions du rapport Gollac (2011) : exigences du travail, exigences émotionnelles, autonomie, rapports sociaux, conflits de valeurs, insécurité.

## Fonctionnalités

- **Questionnaire individuel par agent** : chaque agent sélectionne son unité de travail et répond aux 50 questions avec évaluation de la fréquence d'exposition et de la gravité potentielle (échelles de Likert 1-5).
- **Agrégation en temps réel** : les résultats sont consolidés automatiquement par unité de travail et par famille de risque.
- **Double matrice de criticité** (Fréquence × Gravité) : une pour les risques classiques, une pour les RPS.
- **Synthèses séparées** : tableaux de synthèse distincts pour les risques professionnels et les RPS.
- **Plan d'actions** : génération automatique avec actions préventives suggérées, priorisation par criticité et délais d'intervention.
- **Export** : sauvegarde/chargement JSON, export PDF (impression), export Word du plan d'actions.
- **14 unités de travail prédéfinies** pour les collectivités territoriales (personnalisables).
- **Aucune dépendance externe** : fichier HTML unique, exécutable hors ligne.
- **Stockage local** (localStorage) : les données restent sur le poste de l'utilisateur (conformité RGPD par conception).

## Cadre réglementaire

| Texte | Objet |
|-------|-------|
| Art. L. 4121-1 à L. 4121-5, Code du travail | Obligations générales de prévention |
| Art. L. 4121-3, Code du travail | Évaluation des risques professionnels |
| Art. R. 4121-1 à R. 4121-4, Code du travail | Document unique |
| Décret n° 85-603 du 10 juin 1985 (modifié) | Hygiène et sécurité dans la FPT |
| Rapport Gollac (2011) | Mesure des RPS au travail |
| Loi n° 2021-1018 du 2 août 2021 | Renforcement de la prévention en santé au travail |

## Installation et utilisation

Aucune installation requise. L'application est un fichier HTML autonome.

```bash
# Cloner le dépôt
git clone https://github.com/[USERNAME]/duerp-interactif.git

# Ouvrir directement dans un navigateur
open index.html
# ou
xdg-open index.html
```

Alternativement, accéder à la version en ligne : [referentdeontologue.fr/document-unique](https://www.referentdeontologue.fr/document-unique)

## Architecture technique

```
duerp-interactif/
├── index.html          # Application complète (HTML + CSS + JS)
├── README.md           # Documentation
├── LICENSE             # Licence GPL v3
├── CITATION.cff        # Métadonnées de citation (CFF)
├── codemeta.json       # Métadonnées CodeMeta (Software Heritage / HAL)
├── CHANGELOG.md        # Historique des versions
└── .github/
    └── FUNDING.yml     # Informations de financement
```

**Choix techniques** :
- Application monopage (SPA) sans framework ni dépendance externe
- Vanilla JavaScript ES6+
- CSS natif avec variables et grilles
- Responsive design (mobile-first)
- Stockage côté client uniquement (localStorage)

## Méthodologie d'évaluation

### Risques professionnels

Pour chaque situation dangereuse identifiée par l'agent :
- **Fréquence d'exposition** : de 1 (rare) à 5 (permanente)
- **Gravité potentielle** : de 1 (bénigne) à 5 (critique)
- **Criticité** = Fréquence × Gravité (score de 1 à 25)

### Risques psychosociaux (modèle Gollac)

Même méthodologie appliquée aux 6 dimensions :
1. Intensité et temps de travail (exigences)
2. Exigences émotionnelles
3. Autonomie et marges de manœuvre
4. Rapports sociaux au travail
5. Conflits de valeurs
6. Insécurité de la situation de travail

### Seuils de criticité

| Criticité | Niveau | Action |
|-----------|--------|--------|
| 1 – 4 | 🟢 Faible | Surveillance (12 mois) |
| 5 – 14 | 🟡 Modéré | Action à programmer (3 mois) |
| 15 – 25 | 🔴 Élevé | Action immédiate |

## Contexte de développement

Cet outil a été conçu dans le cadre d'une activité de conseil en déontologie et prévention des risques auprès des collectivités territoriales, en lien avec les travaux de recherche doctorale de l'auteur sur l'éthique et la déontologie dans la fonction publique territoriale (Université de Lorraine / Université de Bourgogne Franche-Comté).

Il fait partie d'une suite d'outils numériques gratuits destinés au secteur public local :
- DUERP (le présent outil)
- DICRIM
- PCS
- Registre des déports
- Charte déontologique (générateur)
- Outil de conformité RGPD

## Auteur

**Louis MATHEVET-BIDINI**

- Doctorant en droit public – Université de Lorraine / Université de Bourgogne Franche-Comté
- Président de l'AP2DFP (Association pour la Promotion de la Déontologie dans la Fonction Publique)
- Secrétaire général de l'ARDT (Association des Référents Déontologues Territoriaux)
- Formateur agréé Ministère de l'Intérieur
- 🌐 [referentdeontologue.fr](https://www.referentdeontologue.fr)

## Citation

Si vous utilisez cet outil dans un contexte académique, merci de le citer :

```bibtex
@software{mathevet-bidini_duerp_2025,
  author       = {Mathevet-Bidini, Louis},
  title        = {{DUERP Interactif -- Document Unique d'Évaluation des Risques Professionnels}},
  year         = {2025},
  version      = {2.0},
  url          = {https://www.referentdeontologue.fr/document-unique},
  license      = {GPL-3.0}
}
```

## Licence

Ce logiciel est distribué sous licence **GNU General Public License v3.0** (GPL-3.0).

Voir le fichier [LICENSE](LICENSE) pour le texte complet.
