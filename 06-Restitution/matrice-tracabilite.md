# Matrice de traçabilité — Module de demande de crédit

**Banque Elyssa (cas fictif)** · **Auteur :** Eya Kanzari — analyste fonctionnelle
**Version :** v1.0
**Objet :** prouver que **chaque exigence remonte à une douleur réelle** et **descente à un écran et
une étape du processus cible** — et inversement, qu'aucun écran ne sert à rien. C'est le livrable
annoncé au [BRD §10](../03-Analyse/BRD.md) (« la matrice complète sera livrée en semaine 6 »).

**Chaîne tracée (approche PMI-BA) :**
`Constat (C) → Douleur (D) → Besoin (B) → Exigence (EF/ENF) → User story (US) → Règle (RG) → Frame wireframe → Étape TO-BE`

---

## 1. Matrice directe — du besoin métier à l'écran

Une ligne par exigence fonctionnelle. Toutes les colonnes sont remplies : **une exigence sans écran
ou sans douleur serait une dérive de périmètre**.

| Exigence | Description courte | ↑ Douleur / besoin | ↓ User stories | Règles | Frames wireframe | Étape TO-BE | Objectif |
|---|---|---|---|---|---|---|---|
| **EF-01** | Formulaire de demande en ligne | D1, D3 / B01 | US-01, US-03 | RG-01, RG-02 | 01, 02, 04, 05, 08 | 1 · Dépôt | O1, O3 |
| **EF-02** | Même formulaire en agence (dépôt assisté) | D3 / B01, B04 | US-04 | RG-02, RG-04 | 10 | 1 · Dépôt | O3 |
| **EF-03** | Référentiel central des pièces | D2 / B02 | US-05 | RG-01 | 11 | 3 · Contrôle | O2 |
| **EF-04** | Contrôle de complétude bloquant | D2 / B02 | US-06, US-14 | RG-01 | 03, 11 | 3 · Contrôle | O2 |
| **EF-05** | Workflow d'états du dossier | D1, D7 / B03, B05 | US-07, US-09 | RG-03, RG-04 | 06, 09, 12 | 4 · Instruction | O1, O4 |
| **EF-06** | Dossier analyste + historique client | D4, D6 / B04 | US-08 | RG-03, RG-05 | 09 | 4 · Instruction | O1 |
| **EF-07** | Portail de suivi + notifications | D1, D5 / B03 | US-02 | RG-03, RG-04 | 06, 07, 08 | 6 · Notification | O4 |
| **EF-08** | Journal horodaté et attribué | D7 / B05 | US-10 | RG-05 | 09, 11, 12 | transverse | — (risque) |
| **EF-09** | Reporting de pilotage continu | D8 / B05 | US-11 | RG-04 | 09 | transverse | O1, O2 |
| **EF-10** | Transmission au comité (inchangé) | D7 / B05 | US-09 | RG-03, RG-04 | 12 | 5 · Comité | O1 |

### Exigences non fonctionnelles (transverses)

| ENF | Exigence | ↓ User stories | Frames / mécanisme |
|---|---|---|---|
| **ENF-01** | Sécurité, droits par rôle | (transverse) | 5 profils distincts dans les frames 09/10/11/12 (client, agent, analyste, risques, comité) |
| **ENF-02** | Protection des données (loi 2004-63) | US-12 | 04 — consentement obligatoire avant soumission (RG-06) |
| **ENF-03** | Disponibilité 99,5 % / 24-7 | (transverse) | hors maquettes — architecture |
| **ENF-04** | Performance ≤ 3 s sur 3G/4G | (transverse) | écrans épurés, maquettes desktop 1440 × 900 livrées, déclinaison mobile 390 × 844 prévue |
| **ENF-05** | Accessibilité + bilingue arabe/français | US-03 | 08 — miroir RTL, cibles tactiles ≥ 44 px |
| **ENF-06** | Journal conservé 10 ans | US-10 | 09/11/12 — « lecture seule, inviolable » (RG-05) |

## 2. Matrice inverse — de la douleur à la couverture (aucune douleur oubliée)

| Douleur | Constats sources | Besoin | Exigences | User stories | Frames | Couverture |
|---|---|---|---|---|---|---|
| **D1** — client sans visibilité | C01, C02, C04 | B01, B03 | EF-01, EF-05, EF-07 | US-01, US-02 | 01, 05, 06, 07 | ✔ complète |
| **D2** — dossiers incomplets | C03, C06, C09 | B02 | EF-03, EF-04 | US-05, US-06, US-14 | 03, 11 | ✔ complète |
| **D3** — saisies multiples | C05, C10 | B01, B04 | EF-01, EF-02 | US-04 | 01, 10 | ✔ complète |
| **D4** — historique inaccessible | C11 | B04 | EF-06 | US-08 | 09 | ✔ complète |
| **D5** — agence saturée de suivi | C07, C15, C17 | B03 | EF-07 | US-02 | 06, 07 | ✔ complète |
| **D6** — temps d'analyse réduit | C12 | B04 | EF-06 | US-08 | 09 | ✔ complète |
| **D7** — aucune traçabilité | C13 | B05 | EF-05, EF-08, EF-10 | US-07, US-09, US-10 | 09, 12 | ✔ complète |
| **D8** — reporting manuel | C14, C16 | B05 | EF-09 | US-11 | 09 | ✔ complète |

**Résultat : 8/8 douleurs P1–P2 couvertes, 10/10 exigences fonctionnelles tracées vers ≥ 1 écran,
14/14 user stories rattachées à ≥ 1 exigence et ≥ 1 frame.** Aucune exigence orpheline (sans
amont), aucun écran orphelin (sans aval).

## 3. Vérification de cohérence — les 7 règles de gestion

| RG | Règle | Frames qui l'appliquent | Étape TO-BE |
|---|---|---|---|
| **RG-01** | Liste de pièces par type depuis le référentiel | 01, 02, 03, 07, 11 | 3 |
| **RG-02** | Un dossier = un numéro, une seule saisie tout canal | 04, 07, 10 | 1–2 |
| **RG-03** | États autorisés : déposé → instruction → comité → décidé → notifié | 06, 09, 12 | 4–5 |
| **RG-04** | Toute transition notifie le client + écrit au journal | 05, 06, 08, 09, 10, 12 | 2, 4, 6 |
| **RG-05** | Journal inviolable, conservation 10 ans | 09, 11, 12 | transverse |
| **RG-06** | Consentement obligatoire avant soumission | 04 | 1 |
| **RG-07** | Interface bilingue arabe/français à parité | 08 | transverse |

## 4. Ce que la matrice a révélé (valeur de la démarche)

- **Aucune fonctionnalité « plaque à collectionner »** : chaque écran du lot wireframes (S5)
  descend d'une douleur mesurée (S3). Les 3 stories Could/Should (US-11, US-13, US-14) sont les
  seules non bloquantes et restent tracées.
- **Un point de vigilance identifié** : EF-09 (reporting) et EF-08 (journal) n'ont **pas d'écran
  dédié** — ils sont portés par le tableau de bord analyste (frame 09) et le référentiel (frame 11).
  À confirmer avec le sponsor : faut-il un **écran de pilotage direction distinct** (frame 13) ou le
  KPI intégré suffit-il ? Décision à trancher en revue S6.
- **La règle RG-04 est la plus critique** : elle relie 6 des 12 frames — c'est le fil conducteur
  « le client n'appelle plus » (D1/D5). Sa défaillance réouvrirait ~2 200 appels/semaine.

## 5. Comment relire cette matrice

- **De haut en bas** (sponsor) : « cette exigence est-elle justifiée ? » → colonne ↑ Douleur.
- **De bas en haut** (développeur / testeur) : « à quoi sert cet écran ? » → colonne ↑ Exigence,
  puis les [critères d'acceptation Gherkin](../04-Exigences/user-stories-backlog.md) de la user story.
- **En cas de contestation** (risque D7) : la chaîne complète constat → écran permet de rejouer
  la décision et de prouver ce qui avait été contrôlé.

---

*Documents liés : [BRD](../03-Analyse/BRD.md) · [user stories](../04-Exigences/user-stories-backlog.md) ·
[wireframes](../05-Solution/wireframes/README.md) · [business case](business-case.md) ·
deck de restitution (11 pages, support oral — envoyé sur demande)*
