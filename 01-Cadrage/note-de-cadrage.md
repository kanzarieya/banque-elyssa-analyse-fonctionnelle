# Note de cadrage — Digitalisation du processus de demande de crédit

| | |
|---|---|
| **Entreprise** | Banque Elyssa (entreprise fictive — cas d'école) |
| **Auteur** | Eya Kanzari — analyste fonctionnelle junior |
| **Date / version** | 19 octobre 2026 — v1.0 |
| **Statut** | Validée (projet solo) |

## 1. Contexte

Banque Elyssa est une banque commerciale fictive de taille moyenne : 40 agences en
Tunisie, environ 250 000 clients, deux segments cibles : particuliers et
micro-entreprises. Le processus de demande de crédit repose aujourd'hui sur des
dossiers papier, des fichiers Excel éclatés et des échanges par téléphone.

## 2. Problème constaté

Constats de départ (chiffres simulés, retenus comme hypothèses de travail — ils seront
confirmés ou ajustés pendant l'élicitation) :

- Délai moyen de traitement d'une demande : **12 jours ouvrés**
- **35 %** des dossiers arrivent incomplets au niveau de l'étude au siège
- Le même dossier est **saisi 3 fois** : fiche agence, fichier Excel du siège, compte-rendu papier
- **60 %** des appels entrants à l'agence sont des demandes de suivi de la part des clients
- Le client n'a **aucune visibilité** sur l'avancement de sa demande
- L'historique de crédit d'un client existant est **introuvable** au moment de l'étude

## 3. Objectifs

**Objectif général :** digitaliser le parcours de demande de crédit de bout en bout pour
réduire les délais, fiabiliser les dossiers et donner une visibilité complète au client.

**Objectifs mesurables (cibles à 6 mois après mise en production simulée) :**

| ID | Objectif | Indicateur | Cible |
|---|---|---|---|
| O1 | Réduire le délai de traitement | Délai moyen constaté | ≤ 5 jours ouvrés |
| O2 | Fiabiliser les dossiers dès le dépôt | Taux de dossiers incomplets | ≤ 10 % |
| O3 | Supprimer les saisies en double | Nombre de saisies par dossier | 1 |
| O4 | Informer le client à chaque étape | Taux de notifications automatiques | 100 % |

## 4. Périmètre

**Dans le périmètre :**

- Dépôt de la demande en agence **et** en ligne (portail client)
- Contrôle de complétude du dossier à l'accueil
- Transmission et étude au siège (analyse, scoring interne)
- Notification du client à chaque changement d'état

**Hors périmètre :**

- Décision finale du comité de crédit (processus existant, inchangé)
- Recouvrement des impayés
- Comptabilisation des crédits accordés
- Crédits immobiliers > 200 000 DT (faible volume, processus spécifique)

## 5. Livrables du projet

1. Note de cadrage + carte des parties prenantes (ce document + `parties-prenantes-raci.md`)
2. Dossier d'élicitation : personas, guides d'entretien, synthèse des constats
3. Cartographie AS-IS en BPMN + matrice des points de douleur + causes racines
4. BRD + user stories + critères d'acceptation + backlog priorisé MoSCoW
5. Processus cible TO-BE en BPMN + matrice de traçabilité
6. Maquettes desktop des écrans clés du parcours digitalisé
7. Mini business case + deck de restitution en slides

## 6. Planning (6 semaines, 5 à 7 h/semaine)

| Semaine | Contenu |
|---|---|
| S1 | Cadrage, parties prenantes, personas, guides d'entretien |
| S2 | Élicitation simulée, synthèse des constats, AS-IS BPMN |
| S3 | Matrice des douleurs, causes racines, BRD |
| S4 | User stories, critères d'acceptation, backlog MoSCoW |
| S5 | TO-BE BPMN, wireframes Figma |
| S6 | Business case, traçabilité, deck executive, publication |

## 7. Méthode et outils

- Approche inspirée du **PMI-BA** (traçabilité besoin → exigence → solution)
- Travail **agile en solo** : backlog hebdomadaire, revue de fin de semaine avec grille de qualité
- Outils : Bizagi Modeler (BPMN), Figma (wireframes), Jira ou Notion (backlog), PowerPoint/Canva (restitution)

## 8. Hypothèses et limites

- La banque, ses chiffres et ses employés sont **fictifs** ; les données sont des
  hypothèses réalistes, explicitement documentées.
- Les entretiens sont **simulés** à partir de personas cohérents (`../02-Elicitation/personas.md`).
- Le dossier vise la démonstration de la démarche pour un poste d'analyste
  fonctionnelle junior — pas la faisabilité technique réelle.

## 9. Risques et parades

| Risque | Parade |
|---|---|
| Dérive du périmètre (ajouts de fonctionnalités) | Tout ajout passe par le backlog avec priorisation MoSCoW |
| Temps disponible limité | Plafond de 7 h/semaine, livrables découpés par semaine |
| Travail sans relecteur | Auto-revue hebdomadaire sur 3 critères : clarté, cohérence avec le BPMN, traçabilité |

## 10. Parties prenantes

Vue d'ensemble (détail dans `parties-prenantes-raci.md`) :

- **Sponsor** : Mme Nadia Jelassi, directrice de la digitalisation
- **Experts métier** : directeur d'agence, responsable des risques, analyste crédit, agent d'accueil
- **Représentant des clients** : Sami Ben Ammar, gérant d'une micro-entreprise
