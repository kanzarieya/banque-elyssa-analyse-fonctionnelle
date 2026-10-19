# Analyse des causes racines — Projet Banque Elyssa

**Date :** 2 novembre 2026 · **Auteur :** Eya Kanzari
**Méthode :** 3 analyses « 5 Pourquoi » sur les douleurs P1 les plus coûteuses
(D1, D2, D4), complétées par une synthèse type Ishikawa sur les 8 douleurs.

## 1. Pourquoi le client n'a-t-il aucune visibilité ? (D1)

1. **Pourquoi ?** Aucune information n'est donnée au client entre le dépôt et la décision.
2. **Pourquoi ?** Le dossier vit sur papier et dans des fichiers Excel : aucun état
   n'est consultable, même en interne.
3. **Pourquoi ?** Il n'existe aucun canal numérique ni workflow de suivi pour le crédit.
4. **Pourquoi ?** La douleur n'a jamais été mesurée : ni indicateur de délai, ni
   mesure de satisfaction.
5. **Pourquoi ?** Personne n'est responsable de la mesure et de l'amélioration du
   processus.

**Cause racine : absence de gouvernance processus.**
→ *Conséquence pour la solution : l'outil doit mesurer nativement (indicateurs),
pas seulement informatiser le papier. « On ne peut pas améliorer ce qu'on ne mesure pas. »*

## 2. Pourquoi un dossier sur trois arrive-t-il incomplet ? (D2)

1. **Pourquoi ?** Les pièces exigées varient selon la personne qui vérifie.
2. **Pourquoi ?** Les règles sont transmises oralement, sans référentiel documenté partagé.
3. **Pourquoi ?** Le processus de demande de crédit n'a jamais été formalisé :
   pas de modèle approuvé, pas de propriétaire.
4. **Pourquoi ?** Les priorités historiques de la banque étaient commerciales,
   pas opérationnelles.
5. **Pourquoi ?** Le coût des allers-retours n'était jamais quantifié.

**Cause racine : absence de référentiel de règles de complétude.**
→ *Conséquence pour la solution : un référentiel de complétude **paramétrable dans
l'outil** (par type de crédit), et non un document PDF figé que personne ne mettra à jour.*

## 3. Pourquoi l'historique client est-il inaccessible ? (D4)

1. **Pourquoi ?** Les anciens dossiers sont sur papier, aux archives physiques.
2. **Pourquoi ?** Ils prédatent les outils actuels et n'ont jamais été numérisés.
3. **Pourquoi ?** Le coût de numérisation était perçu comme élevé.
4. **Pourquoi ?** Aucun gain chiffré ne justifiait l'investissement : le temps de
   recherche n'a jamais été mesuré.
5. **Pourquoi ?** Absence de données de pilotage sur le temps des opérations.

**Cause racine : absence de mesure du temps opérationnel.**
→ *Conséquence pour la solution : historique centralisé **et** KPI de temps de
traitement par étape, pour transformer un coût invisible en gain démontrable.*

## 4. Synthèse type Ishikawa — les 8 douleurs par catégorie de causes

| Catégorie | Causes principales | Douleurs alimentées |
|---|---|---|
| **Processus** | Processus jamais formalisé ; double contrôle de complétude (agence puis siège) ; comité en batch hebdomadaire | D2, D6 |
| **Outils / Systèmes** | Aucun canal web ; fichiers Excel éclatés et multi-versions ; transmission par scan papier | D1, D3 |
| **Données** | Historique papier non numérisé ; pas de source unique par dossier ; pas de référentiel des pièces | D3, D4 |
| **Personnel** | Savoir tacite transmis oralement ; relances téléphoniques ; analyse reportée hors horaires | D2, D5, D6 |
| **Organisation** | Pas de gouvernance processus ; pas d'indicateurs ; priorités historiquement commerciales | D7, D8 |
| **Client / Environnement** | Habitude du guichet papier ; attente forte de visibilité (smartphone d'abord) | D1, D5 |

## 5. Trois principes directeurs pour le BRD

L'analyse des causes racines impose trois exigences transverses, au-delà des
fonctionnalités demandées :

1. **Mesurer par défaut** — tout indicateur utile au pilotage doit être calculé
   nativement par l'outil (délais par étape, taux d'incomplétude, volume).
2. **Un référentiel unique et vivant** — règles de complétude, types de crédit et
   états du dossier sont paramétrables par les métiers, sans développement.
3. **Traçabilité native** — chaque action et chaque contrôle est journalisé
   (qui, quoi, quand), par construction et non en option.

---

*Suite : traduction des besoins en exigences dans le [BRD](BRD.md).*
