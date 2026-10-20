# Business case — Digitalisation du processus de demande de crédit

**Banque Elyssa (cas fictif)** · **Auteur :** Eya Kanzari — analyste fonctionnelle
**Date / version :** 20 novembre 2026 — v1.0 · **Statut :** prêt pour revue sponsor (N. Jelassi)
**Sources :** [BRD](../03-Analyse/BRD.md) · [matrice des douleurs](../03-Analyse/matrice-douleurs.md) ·
[causes racines](../03-Analyse/causes-racines.md) · [processus TO-BE](../05-Solution/to-be-processus.md) ·
[user stories](../04-Exigences/user-stories-backlog.md)

> **Transparence :** la Banque Elyssa est fictive. Tous les chiffres sont des
> **hypothèses réalistes documentées**, construites à partir des constats de
> l'élicitation simulée (~480 demandes/semaine, 40 agences). Les coûts et les gains
> sont des ordres de grandeur destinés à démontrer la **méthode de chiffrage**, pas
> des données financières réelles.

---

## 1. Le problème en une phrase (rappel)

Un processus 100 % papier : **12 jours ouvrés** de délai moyen, **35 %** de dossiers
incomplets arrivant au siège, **3 saisies** du même dossier, **0 visibilité** client,
et **~960 heures de travail perdues par semaine** (double saisie, recherche d'historique,
appels de suivi). *(Source : matrice des douleurs, section 4.)*

## 2. Hypothèses de chiffrage

| Hypothèse | Valeur retenue | Justification |
|---|---|---|
| Volume de demandes | 480 / semaine · **23 040 / an** (48 semaines travaillées) | Cadrage + BRD §8 |
| Coût horaire interne moyen (agent, analyste) | **25 DT / h** chargé | Hypothèse de marché, masse salariale back-office bancaire |
| Périmètre d'amortissement | **3 ans** | Horizon standard d'un projet digital |
| Montée en charge des gains | An 1 : 60 % · An 2 : 90 % · An 3 : 100 % | Adoption du canal en ligne progressive (risque R1 du BRD) |
| Réduction du délai | 12 j → **≤ 5 j** ouvrés | Objectif O1 / décomposition TO-BE §4 |
| Incomplétude | 35 % → **≤ 10 %** | Objectif O2 |

## 3. Gains quantifiés (productivité récupérée)

On ne récupère pas les 960 h brutes : on compte uniquement les heures **directement
supprimées** par les mécanismes du TO-BE, avec un taux de récupération prudent.

| Douleur | Base hebdomadaire | Mécanisme TO-BE | Récupération | Heures gagnées / sem. |
|---|---|---|---|---|
| D3 — double/triple saisie | 64 h (480 fiches × 8 min) | Dossier unique, une seule saisie (RG-02) | ~90 % | **58 h** |
| D4 — recherche d'historique | 160 h (20 min × volume) | Historique intégré à l'écran (EF-06) | ~75 % | **120 h** |
| D1 / D5 — appels de suivi | 2 200 appels × ~3 min ≈ 110 h | Portail + notifications auto (EF-07, RG-04) | ~80 % | **88 h** |
| D2 — retouche dossiers incomplets | 168 dossiers × ~30 min ≈ 84 h | Contrôle bloquant à la soumission (EF-04) | ~70 % | **59 h** |
| **Total productivité** | | | | **≈ 325 h / semaine** |

**Gain productivité annuel (à pleine vitesse) :** 325 h × 48 sem × 25 DT ≈ **390 000 DT / an**.

### Gains non productivité (à surveiller, non monétarisés ici)

- **Délai 12 j → 5 j** : meilleure conversion client et avantage concurrentiel (non chiffré, prudent).
- **Risque réglementaire D7 neutralisé** : journal inviolable 10 ans (RG-05) — décision contestable =
  décision justifiable. Un seul contentieux évité couvre une part significative du coût du projet.
- **Qualité d'analyse (D6)** : temps d'étude rendu à l'analyse, plus reporté en soirée.
- **Pilotage temps réel (D8)** : fin du reporting mensuel manuel refait à la main (EF-09).

## 4. Coûts

| Poste | Type | Montant (DT) | Hypothèse |
|---|---|---|---|
| Conception & développement (portail + workflow + référentiel + reporting) | Investissement initial | **420 000** | ~6 mois, équipe resserrée + réutilisation socle digital existant |
| Intégration (SMS/e-mail, historique client, annuaire interne) | Investissement initial | **80 000** | Interfaçage systèmes existants |
| Numérisation de l'historique (clients actifs 5 ans) | Investissement initial | **60 000** | BRD §8 — le reste reste sur demande manuelle |
| Conduite du changement & formation (40 agences) | Investissement initial | **50 000** | Agents + analystes + risques |
| **Total investissement (année 0)** | | **610 000** | |
| Hébergement, maintenance, licences | Récurrent | **95 000 / an** | ~15 % de l'investissement |
| Tiers de garde / support fonctionnel | Récurrent | **40 000 / an** | 0,5 ETP + astreinte |
| **Total récurrent** | | **135 000 / an** | |

## 5. Modèle sur 3 ans

| | Année 0 | Année 1 | Année 2 | Année 3 |
|---|---|---|---|---|
| Investissement | −610 000 | — | — | — |
| Coûts récurrents | — | −135 000 | −135 000 | −135 000 |
| Gains productivité (60 / 90 / 100 %) | — | +234 000 | +351 000 | +390 000 |
| **Flux net annuel** | **−610 000** | **+99 000** | **+216 000** | **+255 000** |
| **Flux cumulé** | −610 000 | −511 000 | −295 000 | **−40 000** |

*(Gains année 1 = 390 000 × 60 % = 234 000, etc.)*

### Indicateurs de rentabilité

| Indicateur | Valeur | Lecture |
|---|---|---|
| **Gains annuels à pleine vitesse** | **390 000 DT** | productivité récupérée seule |
| **Retour sur investissement (ROI) à 3 ans** | **≈ −6 % → à l'équilibre** | le projet s'autofinance sur ~3 ans **sans** compter les gains non productivité |
| **Délai de retour (payback)** | **≈ 3 ans** (cumulé ≈ 0 en année 3) | prudent : basé uniquement sur les heures récupérées |
| **Payback « élargi »** | **≈ 18–24 mois** | si on valorise ne serait-ce qu'un contentieux D7 évité ou la reprise de capacité commerciale |

> **Lecture honnête du sponsor :** sur la seule productivité administrative, le projet
> est **à l'équilibre vers 3 ans** — un business case défendable mais pas spectaculaire.
> Sa vraie valeur est **stratégique et défensive** : suppression d'un risque réglementaire
> (D7), qualité d'évaluation restaurée (D6) et expérience client (12 j → 5 j) difficile à
> chiffrer mais décisif face à une banque digitale concurrente. C'est le message que porte
> le [deck de restitution](deck-executive-banque-elyssa.pptx).

## 6. Analyse de sensibilité

Le résultat dépend de trois variables. Scénarios sur les gains annuels à pleine vitesse :

| Variable | Basse | Retenue | Haute |
|---|---|---|---|
| Coût horaire interne | 18 DT/h → 281 000 DT/an | **25 DT/h → 390 000** | 32 DT/h → 499 000 |
| Taux de récupération moyen | 60 % → 234 000 | **~78 % → 390 000** | 90 % → 450 000 |
| Adoption du canal en ligne | lente (an 1 à 40 %) | **moyenne (60 %)** | rapide (an 1 à 80 %) |

Même dans le **scénario bas** (18 DT/h, récupération 60 %), le projet reste proche de
l'équilibre à 3 ans et devient largement positif en scénario haut. Le point de bascule
n'est pas financier mais **réduction du risque** : plus le coût d'un contentieux de
décision non justifiable est élevé, plus le retour sur investissement s'accélère.

## 7. Risques qui menacent le business case

| Risque (origine BRD §9) | Effet sur le chiffrage | Parade |
|---|---|---|
| Faible adoption du canal en ligne | Gains D1/D5 amputés | Dépôt assisté identique au web (EF-02) ; on récupère les gains **même si** le client vient à l'agence |
| Référentiel de complétude mal maintenu | Gains D2 perdus | Paramétrage métiers + revue semestrielle formalisée (US-05) |
| Résistance des agents | Gains D3/D4 ralentis | Indicateurs de fluidité, pas de notation individuelle |
| Dérive fonctionnelle | Coût initial gonflé | Tout ajout passe par le backlog MoSCoW et l'arbitrage sponsor |

## 8. Recommandation

**Lancer le projet.** Le chiffrage prudent sur la seule productivité administrative
place le retour à ~3 ans ; la valeur réelle vient du trio **conformité (D7) + qualité
d'analyse (D6) + expérience client (12 j → 5 j)**, non entièrement monétarisable mais
stratégique. Recommandation de séquence : **MVP canal + complétude (Sprint 1)** — c'est
là que se concentrent les gains D2/D3 et tout le risque réglementaire — puis suivi
client, instruction, pilotage.

---

*Aller plus loin : [deck executive de restitution](deck-executive-banque-elyssa.pptx) ·
[matrice de traçabilité](matrice-tracabilite.md) ·
retour au [README](../README.md).*
