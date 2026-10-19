# Synthèse executive — Digitalisation de la demande de crédit

**Banque Elyssa (cas fictif)** · **Pour :** comité de direction / sponsor N. Jelassi
**Auteur :** Eya Kanzari — analyste fonctionnelle · **Date :** 20 novembre 2026
**À lire si vous avez 3 minutes.** Détail dans le [business case](business-case.md) et la
[matrice de traçabilité](matrice-tracabilite.md).

---

## Le problème

Traiter une demande de crédit coûte **12 jours**, un dossier sur trois arrive **incomplet** au
siège, chaque dossier est **saisi 3 fois**, le client **ne sait jamais où en est sa demande** —
et appelle l'agence pour le découvrir. Coût total : **~960 heures de travail perdues par semaine**
et une file d'agence transformée en guichet de renseignements.

## Ce que la solution change

Un portail de demande unique, **mobile d'abord et bilingue arabe/français**, qui fait la même
chose en agence et en ligne :

1. Le client dépose **une seule fois**, reçoit un **récépissé immédiat** (numéro de dossier).
2. Le système **bloque toute demande incomplète** à la soumission, avec la liste exacte des
   pièces manquantes — plus de dossier qui part au siège par erreur.
3. Le client **suit sa demande en temps réel** et est notifié à chaque étape (SMS/e-mail).
4. L'analyste travaille sur **un dossier unique avec l'historique client intégré**.
5. **Chaque contrôle est journalisé** (qui, quoi, quand, 10 ans) : une décision refusée devient
   une décision **justifiable** — c'est le risque réglementaire qui disparaît.

## Résultats cibles (6 mois après mise en production)

| Indicateur | Aujourd'hui | Cible |
|---|---|---|
| Délai moyen de traitement | 12 jours ouvrés | **≤ 5 jours** |
| Dossiers incomplets au siège | 35 % | **≤ 10 %** |
| Saisies du même dossier | 3 | **1** |
| Client notifié à chaque étape | 0 % | **100 %** |
| Appels de suivi / semaine | ~2 200 | **quasi nuls** |

## Combien ça coûte, ce que ça rapporte

- **Investissement :** ~610 000 DT · **récurrent :** ~135 000 DT/an.
- **Gain productivité seul :** ~390 000 DT/an (≈ 325 h/semaine récupérées).
- **Retour sur la seule productivité administrative : ~3 ans** — un business case **défendable
  mais pas spectaculaire**.
- **La vraie valeur est défensive et stratégique :** suppression du risque de contentieux
  (décisions non justifiables), qualité d'évaluation restaurée, expérience client 12 j → 5 j.
  En intégrant ces gains, le retour descend à **18–24 mois**.

## Recommandation

**Lancer le projet, en commençant par le MVP « dépôt + contrôle de complétude »** (Sprint 1 du
[backlog](../04-Exigences/user-stories-backlog.md)) : c'est là que se concentrent les gains
D2/D3 et **tout le risque réglementaire**. Le reste (suivi, instruction, pilotage) s'enchaîne en
sprints 2 à 4.

## Décision attendue du sponsor

1. Valider le **périmètre** (décision du comité de crédit inchangée — hors solution).
2. Arbitrer **un point ouvert** : faut-il un écran de pilotage direction distinct, ou les
   indicateurs intégrés au tableau de bord analyste suffisent-ils ? *(voir matrice §4)*
3. Confirmer les **hypothèses de chiffrage** (coût horaire 25 DT, adoption progressive).

---

*Cas fictif — chiffres = hypothèses réalistes documentées. Retour au [README](../README.md).*
