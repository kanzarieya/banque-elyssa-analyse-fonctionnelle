# Matrice des douleurs — Projet Banque Elyssa

**Date :** 2 novembre 2026 · **Auteur :** Eya Kanzari
**Source :** [synthèse des 17 constats](../02-Elicitation/synthese-constats.md)

> Cas fictif — les impacts chiffrés sont des **hypothèses réalistes** documentées,
> basées sur ~480 demandes de crédit par semaine (40 agences × 12 demandes).

## 1. Méthode

Les 17 constats sont consolidés en **8 douleurs métier**. La fréquence et la gravité
d'une douleur héritent du constat le plus sévère de son groupe. Score = F × G
(3/2/1 chacune). Seuil de priorisation : score ≥ 6, ou douleur à risque réglementaire.

## 2. Les huit douleurs

| ID | Douleur métier | Constats | F | G | Score | Impact chiffré (hypothèse) | Priorité |
|---|---|---|---|---|---|---|---|
| **D1** | Parcours client sans visibilité : déplacements répétés, aucun suivi, pas de récépissé | C01, C02, C04 | 3 | 3 | **9** | ~720 déplacements clients et ~2 200 appels de suivi par semaine | **P1** |
| **D2** | Règles de complétude incohérentes : 1 dossier sur 3 incomplet, double rejet | C03, C06, C09 | 3 | 3 | **9** | ~168 dossiers incomplets/semaine, +2 à 5 jours de délai chacun | **P1** |
| **D3** | Saisies multiples et données éclatées : fiche papier + Excel, 3 versions du fichier | C05, C10 | 3 | 2 | 6 | ~64 h/semaine de double saisie (480 fiches × 8 min) | **P1** |
| **D4** | Historique client inaccessible : 20 min de recherche aux archives par dossier | C11 | 3 | 3 | **9** | ~160 h/semaine perdues (≈ 4,5 ETP) | **P1** |
| **D5** | File d'attente d'agence saturée par les suivis de dossier | C07, C15, C17 | 3 | 2 | 6 | Capacité commerciale absorbée : ~2 200 appels de suivi/semaine | P2 |
| **D6** | Temps d'analyse réduit par les tâches manuelles | C12 | 3 | 2 | 6 | Étude reportée en soirée → risque qualité d'évaluation | P2 |
| **D7** | Aucune traçabilité des contrôles : décisions non justifiables | C13 | 2 | 3 | 6 | Risque réglementaire et contentieux → **priorité P1 par nature** | **P1** |
| **D8** | Reporting manuel et tardif, délais non mesurés | C14, C16 | 2 | 3 | 6 | Pilotage mensuel au lieu de temps réel | P2 |

## 3. Quadrant fréquence × gravité

```
 Gravité élevée │   D7 · D8        │   D1 · D2 · D4
                │                  │
 Gravité moyenne │                  │   D3 · D5 · D6
                └──────────────────┴────────────────────
                  Fréquence moyenne     Fréquence élevée
```

**Zone rouge (haute fréquence + haute gravité) : D1, D2, D4.** C'est là que le
projet doit commencer. D7 rejoint la priorité malgré une fréquence moyenne, car
le risque est réglementaire : une décision contestée non justifiable peut coûter
plus cher qu'un mois de retards.

## 4. Ce que la matrice change dans l'argumentaire

Avant, la demande était « il faut un outil ». Maintenant, le sponsor peut trancher
sur des chiffres : « On attaque d'abord D1, D2, D4 et D7, parce qu'ensemble ils
représentent ~960 heures de travail perdues par semaine et l'intégralité du risque
client et réglementaire. »

## 5. Suite

Chaque douleur P1 devient un **besoin métier** (B01 à B05) dans le
[BRD](BRD.md). Les douleurs P2 (D3 en partie, D5, D6, D8) alimentent le backlog
priorisé MoSCoW de la semaine 4.

---

*Voir l'analyse des causes racines : [`causes-racines.md`](causes-racines.md)*
