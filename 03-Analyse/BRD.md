# BRD — Business Requirements Document

## Module de demande de crédit digitalisée

| | |
|---|---|
| **Projet** | Digitalisation du processus de demande de crédit — Banque Elyssa (cas fictif d'école) |
| **Auteur** | Eya Kanzari — analyste fonctionnelle |
| **Date / version** | 2 novembre 2026 — v0.9 **en attente de revue sponsor** |
| **Périmètre** | Du dépôt de la demande à la notification du client (décision du comité hors périmètre) |

## 1. Contexte et problème métier

Le processus actuel (décrit dans [la cartographie AS-IS](as-is-processus.md)) repose
sur le papier, les fichiers Excel éclatés et les relances téléphoniques. Les
conséquences mesurées (hypothèses documentées) :

- Délai moyen de traitement : **12 jours ouvrés** (cible : ≤ 5)
- **35 %** des dossiers arrivent incomplets au siège (cible : ≤ 10 %)
- Chaque dossier est saisi **3 fois** (cible : 1)
- **0 %** de visibilité pour le client entre dépôt et décision (cible : 100 % notifié)
- ~**960 heures de travail perdues par semaine** (double saisie, recherches d'historique, appels de suivi)

## 2. Objectifs métier

| ID | Objectif | Indicateur | Cible à 6 mois |
|---|---|---|---|
| O1 | Réduire le délai de traitement | Délai moyen constaté | ≤ 5 jours ouvrés |
| O2 | Fiabiliser les dossiers dès le dépôt | Taux de dossiers incomplets au siège | ≤ 10 % |
| O3 | Supprimer les saisies multiples | Nombre de saisies par dossier | 1 |
| O4 | Informer le client à chaque étape | Taux de notifications automatiques | 100 % |

## 3. Besoins métier (issus des douleurs prioritaires P1)

| ID | Besoin métier | Douleurs / constats sources | Bénéfice attendu |
|---|---|---|---|
| **B01** | Permettre au client de déposer sa demande une seule fois, en ligne ou en agence, et recevoir un récépissé immédiat | D1 (C01, C02, C04) | Fin des déplacements répétés ; preuve de dépôt |
| **B02** | Vérifier la complétude du dossier automatiquement, dès le dépôt, selon des règles centralisées et paramétrables | D2 (C03, C06, C09) | Taux d'incomplétude divisé par 3 ; fin des relances |
| **B03** | Donner au client une visibilité en temps réel sur l'avancement, avec notification à chaque changement d'état | D1 (C02), D5 (C07, C15) | ~2 200 appels de suivi évités par semaine |
| **B04** | Donner à l'analyste un dossier unique intégrant l'historique client | D3 (C05, C10), D4 (C11) | ~160 h/semaine récupérées ; qualité d'analyse |
| **B05** | Tracer chaque contrôle et produire automatiquement les indicateurs de pilotage | D7 (C13), D8 (C14, C16) | Décisions justifiables ; pilotage en temps réel |

## 4. Exigences fonctionnelles de haut niveau

| ID | Exigence | Besoin | Priorité MoSCoW indicative |
|---|---|---|---|
| EF-01 | Formulaire de demande en ligne (particulier et micro-entreprise), mobile d'abord | B01 | Must |
| EF-02 | Formulaire identique utilisable en agence par l'agent (dépôt assisté, pas de double saisie) | B01 | Must |
| EF-03 | Référentiel central des pièces, par type de crédit, paramétrable par les métiers | B02 | Must |
| EF-04 | Contrôle de complétude automatique à la soumission, avec liste exacte des pièces manquantes | B02 | Must |
| EF-05 | Workflow d'états du dossier (déposé → en instruction → au comité → décidé → notifié) | B03, B05 | Must |
| EF-06 | Tableau de bord analyste : dossier unique, historique client intégré, pièces consultables | B04 | Must |
| EF-07 | Portail de suivi client avec notifications automatiques (portail, e-mail, SMS) à chaque changement d'état | B03 | Must |
| EF-08 | Journal horodaté et attribué de chaque action et contrôle (qui, quoi, quand) | B05 | Must |
| EF-09 | Reporting de pilotage continu : délais par étape, taux d'incomplétude, volumes | B05 | Should |
| EF-10 | Transmission du dossier au comité de crédit existant (sans modifier sa décision) | B05 | Must |

## 5. Exigences non fonctionnelles

| ID | Exigence | Détail |
|---|---|---|
| ENF-01 | **Sécurité** | Chiffrement des données en transit et au repos ; authentification forte pour les agents et analystes ; droits d'accès par rôle (client, agent, analyste, risques, direction) |
| ENF-02 | **Protection des données personnelles** | Conformité à la loi tunisienne n° 2004-63 relative à la protection des données à caractère personnel ; consentement explicite du client au dépôt |
| ENF-03 | **Disponibilité** | Service accessible 99,5 % du temps ouvré ; portail client accessible 24/7 en consultation |
| ENF-04 | **Performance** | Temps de réponse ≤ 3 secondes par écran sur connexion 3G/4G |
| ENF-05 | **Accessibilité et langues** | Interface bilingue **arabe / français** ; parcours utilisable sur smartphone bas de gamme |
| ENF-06 | **Traçabilité technique** | Journalisation conservée 10 ans (durée de contestation des décisions de crédit) |

## 6. Périmètre

**Inclus :** dépôt en ligne et en agence, contrôle de complétude, workflow d'instruction,
intégration de l'historique client, notifications, traçabilité, reporting de pilotage.

**Exclus :** décision du comité de crédit (processus existant inchangé), recouvrement
des impayés, comptabilisation, crédits immobiliers > 200 000 DT.

## 7. Critères de succès du projet

Le projet sera déclaré réussi si, 6 mois après mise en production : O1 à O4 sont
atteints **et** aucune régression n'est constatée sur le canal agence (volume de
dépôits assistés stable) **et** la satisfaction client mesurée par enquête progresse
d'au moins 20 points.

## 8. Hypothèses et contraintes

- Volumes : ~480 demandes/semaine, pics saisonniers (rentrée, fêtes) ×1,5.
- Les règles de complétude seront validées par la responsable des risques (S. Bouzid).
- Le canal agence reste obligatoire : aucun client ne peut être contraint au web.
- Les données historiques papier seront numérisées pour les clients actifs des
  5 dernières années ; le reste reste consultable sur demande manuelle.

## 9. Risques métier

| Risque | Probabilité | Impact | Parade |
|---|---|---|---|
| Faible adoption du canal en ligne par les clients habitués au guichet | Haute | Moyen | Dépôt assisté en agence identique au parcours web (EF-02) ; accompagnement |
| Résistance des agents (crainte de surveillance) | Moyenne | Haut | Cadrer les indicateurs comme outils de fluidité, pas de notation individuelle (point validé en cadrage) |
| Référentiel de complétude mal maintenu | Moyenne | Haut | Paramétrage par les métiers + revue semestrielle formalisée |
| Dérive fonctionnelle (ajouts hors périmètre) | Moyenne | Moyen | Tout ajout passe par le backlog MoSCoW et l'arbitrage du sponsor |

## 10. Traçabilité

Constats (C01–C17) → douleurs (D1–D8) → besoins (B01–B05) → exigences (EF/ENF) →
user stories (semaine 4). La matrice complète sera livrée en semaine 6.

---

*Documents liés : [matrice des douleurs](matrice-douleurs.md) ·
[causes racines](causes-racines.md) · [AS-IS](as-is-processus.md) ·
[parties prenantes](../01-Cadrage/parties-prenantes-raci.md)*
