# User stories + backlog MoSCoW — Module de demande de crédit

**Date :** 9 novembre 2026 · **Auteur :** Eya Kanzari
**Source :** [BRD v0.9](../03-Analyse/BRD.md) — exigences EF-01 à EF-10

> Cas fictif — Banque Elyssa. Critères d'acceptation rédigés en **Gherkin**
> (Given/When/Then) pour être directement exploitables en recette.

## 1. Méthode

- Format : « En tant que … je veux … afin de … », conforme aux principes **INVEST**
- Chaque user story est **tracée** vers une exigence fonctionnelle (EF) du BRD et un
  besoin métier (B0x)
- Critères d'acceptation en Gherkin : chaque scénario est vérifiable tel quel
- Estimation en story points (suite de Fibonacci), à affiner en planification

## 2. Épiques

| ID | Épique | Exigences |
|---|---|---|
| EP-01 | Parcours client en ligne | EF-01, EF-04, EF-07 |
| EP-02 | Dépôt assisté en agence | EF-02 |
| EP-03 | Référentiel et contrôle de complétude | EF-03, EF-04 |
| EP-04 | Instruction analyste et comité | EF-05, EF-06, EF-10 |
| EP-05 | Traçabilité et pilotage | EF-08, EF-09 |

## 3. User stories et critères d'acceptation

### EP-01 — Parcours client en ligne

**US-01 — Déposer une demande en ligne** · *EF-01 · B01 · Must · 8 pts*
En tant que **client**, je veux déposer ma demande de crédit en ligne afin d'éviter
les déplacements répétés à l'agence.

```gherkin
Scénario: dépôt complet
  Étant donné un client identifié sur le portail
  Quand il remplit le formulaire, joint les pièces requises et soumet
  Alors la demande est enregistrée avec un numéro de dossier unique
  Et il reçoit un récépissé téléchargeable et par e-mail

Scénario: sauvegarde et reprise du brouillon
  Étant donné un client dont la session est interrompue
  Quand il se reconnecte
  Alors son brouillon est intact et il peut soumettre sans resaisir
```

**US-02 — Suivre l'avancement et être notifié** · *EF-07 · B03 · Must · 5 pts*
En tant que **client**, je veux voir l'état de ma demande et être notifié à chaque
changement afin de ne plus appeler l'agence pour un suivi.

```gherkin
Scénario: notification de changement d'état
  Étant donné une demande au statut "en instruction"
  Quand l'analyste la passe au statut "au comité"
  Alors le client reçoit une notification (portail, e-mail, SMS au choix)
  Et la notification indique le nouvel état et la date prévue de réponse

Scénario: consultation du suivi
  Quand le client consulte son dossier
  Alors il voit l'état actuel, l'historique des étapes et les pièces manquantes éventuelles
```

**US-03 — Utiliser le portail en arabe sur smartphone** · *EF-01, ENF-05 · B01 · Must · 3 pts*
En tant que **client arabophone utilisant un smartphone**, je veux un portail en
arabe, fluide sur mobile, afin de faire ma démarche dans ma langue sans ordinateur.

```gherkin
Scénario: bascule de langue
  Quand le client choisit l'arabe dans l'en-tête
  Alors toute l'interface, y compris les libellés des pièces, s'affiche en arabe
```

### EP-02 — Dépôt assisté en agence

**US-04 — Déposer au guichet sans double saisie** · *EF-02 · B01 · Must · 5 pts*
En tant qu'**agent d'accueil**, je veux saisir la demande du client dans le même
formulaire que le portail afin qu'elle soit visible au siège sans nouvelle saisie.

```gherkin
Scénario: dépôt assisté
  Étant donné un client sans compte portail qui se présente au guichet
  Quand l'agent complète le formulaire avec lui et soumet
  Alors le dossier est créé une seule fois et visible immédiatement au siège
  Et le client reçoit son numéro de dossier et son récépissé par SMS
```

### EP-03 — Référentiel et contrôle de complétude

**US-05 — Maintenir le référentiel des pièces** · *EF-03 · B02 · Must · 3 pts*
En tant que **responsable des risques**, je veux gérer la liste des pièces par type
de crédit afin que les règles de complétude soient centralisées et à jour.

```gherkin
Scénario: ajout d'une pièce obligatoire
  Étant donné que la responsable des risques ajoute "attestation de revenus"
    aux pièces du crédit à la consommation
  Quand un client soumet une nouvelle demande de ce type
  Alors cette pièce est exigée dès le dépôt
  Et les demandes en cours affichent un avertissement sans être bloquées
```

**US-06 — Bloquer la soumission d'un dossier incomplet** · *EF-04 · B02 · Must · 5 pts*
En tant qu'**agent d'accueil**, je veux que le système vérifie la complétude à la
soumission afin de ne plus envoyer de dossiers incomplets au siège.

```gherkin
Scénario: soumission avec pièce manquante
  Étant donné un type de crédit exigeant fiche de paie et extrait bancaire
  Quand une demande est soumise sans l'extrait bancaire
  Alors la soumission est bloquée
  Et la liste exacte des pièces manquantes s'affiche avec la règle appliquée
```

### EP-04 — Instruction analyste et comité

**US-07 — Faire avancer le dossier dans le workflow** · *EF-05 · B03, B05 · Must · 3 pts*
En tant qu'**analyste crédit**, je veux faire passer le dossier d'un état à l'autre
afin que le client soit notifié et que chaque transition soit tracée.

```gherkin
Scénario: transition tracée et notifiée
  Quand l'analyste passe le dossier de "déposé" à "en instruction"
  Alors l'action est journalisée (utilisateur, date, commentaire)
  Et le client est notifié automatiquement
```

**US-08 — Étudier un dossier unique avec l'historique client** · *EF-06 · B04 · Must · 8 pts*
En tant qu'**analyste crédit**, je veux un écran unique avec le dossier et
l'historique complet du client afin de ne plus chercher aux archives.

```gherkin
Scénario: consultation de l'historique
  Étant donné un client de la banque depuis 8 ans
  Quand l'analyste ouvre son dossier d'étude
  Alors il voit ses crédits passés, ses remboursements et les incidents
  Et ce sans quitter l'écran ni consulter de classeur papier
```

**US-09 — Transmettre le dossier au comité** · *EF-10 · B05 · Must · 3 pts*
En tant qu'**analyste crédit**, je veux transmettre le dossier complet au comité
afin qu'il décide avec toutes les informations, sans changer son processus.

```gherkin
Scénario: transmission complète
  Quand le dossier passe au statut "au comité"
  Alors le comité reçoit le dossier, l'avis de l'analyste et l'historique client
  Et la décision reste saisie manuellement par le comité (inchangé)
```

### EP-05 — Traçabilité et pilotage

**US-10 — Auditer un dossier contesté** · *EF-08 · B05 · Must · 5 pts*
En tant que **responsable des risques**, je veux consulter le journal complet d'un
dossier afin de justifier chaque décision en cas de contestation.

```gherkin
Scénario: dossier contesté par le client
  Étant donné un client qui conteste le refus de sa demande
  Quand la responsable des risques ouvre le journal du dossier
  Alors elle voit chaque contrôle effectué, par qui, à quelle date, avec quel résultat
  Et aucune entrée du journal ne peut être modifiée ou supprimée
```

**US-11 — Piloter avec des indicateurs en continu** · *EF-09 · B05 · Should · 5 pts*
En tant que **directeur d'agence**, je veux un tableau de bord des délais et des
dossiers incomplets afin de piloter sans attendre le reporting mensuel.

```gherkin
Scénario: indicateur de délai par étape
  Quand la direction ouvre le tableau de bord
  Alors elle voit le délai moyen par étape sur les 30 derniers jours
  Et le taux de dossiers incomplets à la soumission
```

**US-12 — Consentement aux données personnelles** · *ENF-02 · B01 · Must · 2 pts*
En tant que **client**, je ne veux soumettre ma demande qu'après avoir consenti
explicitement au traitement de mes données personnelles.

```gherkin
Scénario: consentement obligatoire
  Quand je soumets ma demande sans avoir coché le consentement
  Alors la soumission est bloquée avec un message explicite
```

**US-13 — Exporter le récépissé en PDF** · *EF-01 · B01 · Could · 2 pts*
En tant que **client**, je veux télécharger mon récépissé en PDF afin de garder une
preuve de dépôt consultable hors connexion.

**US-14 — Relancer automatiquement les pièces manquantes** · *EF-04, EF-07 · B02 · Should · 3 pts*
En tant que **client**, je veux recevoir un rappel automatique après 7 jours si ma
demande attend des pièces, afin de ne pas la laisser dormir.

## 4. Règles de gestion extraites

| ID | Règle |
|---|---|
| RG-01 | Chaque type de crédit a une liste de pièces définie dans le référentiel ; toute modification prend effet immédiatement pour les nouvelles demandes |
| RG-02 | Un dossier porte un numéro unique et une seule saisie, quel que soit le canal (web ou agence) |
| RG-03 | Les états autorisés : déposé → en instruction → au comité → décidé (accord/refus) → notifié |
| RG-04 | Toute transition d'état déclenche une notification client et une entrée de journal |
| RG-05 | Le journal est inviolable : aucune modification ni suppression, conservation 10 ans |
| RG-06 | Le consentement au traitement des données est obligatoire avant toute soumission |
| RG-07 | L'interface est bilingue arabe/français à parité fonctionnelle |

## 5. Backlog priorisé MoSCoW

| ID | User story | Épique | EF | Besoin | MoSCoW | Points |
|---|---|---|---|---|---|---|
| US-01 | Déposer une demande en ligne | EP-01 | EF-01 | B01 | **Must** | 8 |
| US-02 | Suivre et être notifié | EP-01 | EF-07 | B03 | **Must** | 5 |
| US-03 | Portail arabe sur smartphone | EP-01 | EF-01 | B01 | **Must** | 3 |
| US-04 | Dépôt assisté sans double saisie | EP-02 | EF-02 | B01 | **Must** | 5 |
| US-05 | Référentiel des pièces | EP-03 | EF-03 | B02 | **Must** | 3 |
| US-06 | Blocage si dossier incomplet | EP-03 | EF-04 | B02 | **Must** | 5 |
| US-07 | Workflow d'états | EP-04 | EF-05 | B03, B05 | **Must** | 3 |
| US-08 | Dossier unique + historique | EP-04 | EF-06 | B04 | **Must** | 8 |
| US-09 | Transmission au comité | EP-04 | EF-10 | B05 | **Must** | 3 |
| US-10 | Journal d'audit | EP-05 | EF-08 | B05 | **Must** | 5 |
| US-12 | Consentement données | EP-01 | ENF-02 | B01 | **Must** | 2 |
| US-11 | Tableau de bord pilotage | EP-05 | EF-09 | B05 | Should | 5 |
| US-14 | Rappel pièces manquantes | EP-03 | EF-04 | B02 | Should | 3 |
| US-13 | Récépissé PDF | EP-01 | EF-01 | B01 | Could | 2 |

### Hors périmètre volontaire (Won't, cette version)

| Élément | Justification |
|---|---|
| Scoring automatique / décision automatisée | Ligne rouge des risques : la décision reste humaine et justifiable (C13) |
| Application mobile native | Le portail web mobile suffit (ENF-04) ; une app serait du surcoût |
| Signature électronique | Nécessite un cadre juridique interne non encore défini dans le cas d'école |
| Intégration temps réel avec la centrale des risques externe | Hors périmètre du BRD ; traité comme évolution ultérieure |

## 6. Proposition de découpage en sprints

| Sprint | Contenu | Points |
|---|---|---|
| Sprint 1 (MVP) | US-01, US-04, US-05, US-06, US-12 — déposer un dossier complet, quel que soit le canal | 23 |
| Sprint 2 | US-02, US-03, US-07, US-09 — visibilité client et workflow | 14 |
| Sprint 3 | US-08, US-10 — instruction et audit | 13 |
| Sprint 4 | US-11, US-14, US-13 — pilotage et finitions | 10 |

**Total : 60 points.** La définition de « fini » retenue : code + critères
d'acceptation Gherkin passants + journalisation effective + revue métier.

---

*Semaine suivante : processus cible TO-BE en BPMN et wireframes Figma.*
