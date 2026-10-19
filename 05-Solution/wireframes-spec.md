# Spécification des wireframes — Module de demande de crédit

**Date :** 16 novembre 2026 · **Auteur :** Eya Kanzari
**Outil :** Figma · **Niveau de fidélité :** low-fi (gris, structure et parcours d'abord)

> Cas fictif — Banque Elyssa. Cette spécification décrit les 4 écrans à maquetter
> dans Figma, écran par écran : contenu, états, règles. Chaque écran référence ses
> user stories et règles de gestion pour garder la traçabilité.

## Principes transverses

- **Mobile d'abord** pour le client (ENF-04, ENF-05) : frames 390 × 844
- **Bilingue arabe / français** (RG-07) : prévoir la **mise en miroir RTL** pour
  l'arabe — navigation, icônes directionnelles et alignements inversés
- Cibles tactiles ≥ 44 px, contrastes AA, libellés simples
- L'analyste travaille sur desktop : frames 1440 × 900

## Écran 1 — Dépôt client mobile *(US-01, US-03, US-06, US-12 · RG-01, RG-06)*

**Parcours :** stepper en 3 étapes.

1. **Type de crédit et montant** — sélecteur de type (conso, trésorerie PME…),
   champ montant avec aide « combien coûte votre crédit ? », durée souhaitée.
2. **Pièces justificatives** — checklist générée depuis le référentiel : chaque pièce
   avec bouton « photographier » ou « téléverser ». États : manquant (gris),
   reçu (vert), refusé format illisible (rouge + explication).
3. **Récapitulatif** — tableau des pièces, case de **consentement obligatoire**
   (lien vers la politique de confidentialité, RG-06), bouton « Soumettre ».

**États à dessiner :**
- Brouillon : bandeau « brouillon enregistré », reprise à l'identique
- Soumission bloquée : liste exacte des manquants + règle appliquée (US-06)
- Succès : écran de confirmation avec **numéro de dossier**, récépissé
  téléchargeable (US-13 en Could), prochaines étapes expliquées

## Écran 2 — Suivi client mobile *(US-02, US-14 · RG-03, RG-04)*

**Contenu :**
- En-tête : numéro de dossier, type de crédit, montant
- **Timeline verticale** des états (déposé → en instruction → au comité → décidé)
  avec dates passées et date prévue sur l'étape courante
- Alertes : pièces manquantes (bouton « compléter »), rappel automatique J+7
- Historique des notifications reçues

**État vide :** « Aucune demande en cours » + bouton « Faire une demande ».

## Écran 3 — Tableau de bord analyste desktop *(US-07, US-08, US-10 · RG-03, RG-04, RG-05)*

**Contenu :**
- **File de travail** : tableau triable (ancienneté, état, type), filtres,
  file « à instruire » en priorité ; les transitions disponibles s'affichent
  dans la ligne (RG-03)
- **Écran dossier**, 3 onglets :
  - *Dossier* : demande, pièces visualisables, avis à saisir avant transmission
  - *Historique client* : crédits passés, remboursements, incidents (US-08)
  - *Journal* : qui, quoi, quand — lecture seule (US-10, RG-05)
- Boutons de transition avec commentaire obligatoire, déclencheur de
  notification client automatique (RG-04)

## Écran 4 — Dépôt assisté agence desktop *(US-04 · RG-02)*

- Recherche client existant (évite les doublons) puis **le même formulaire que
  l'écran 1** — c'est le point clé : un seul formulaire, une seule saisie
- Après soumission : récépissé envoyé par **SMS** au client, même sans compte portail

## Livrable Figma attendu

4 frames clients (mobile) + 2 frames analyste/agence (desktop), en niveaux de gris,
nommées `US-01 Dépôt`, `US-02 Suivi`, `US-08 Tableau de bord analyste`,
`US-04 Dépôt assisté`. Un lien de partage en **lecture seule** sera ajouté au
README en semaine 6.

---

*Modèle de processus : [to-be-processus.md](to-be-processus.md) · Retour aux
[user stories](../04-Exigences/user-stories-backlog.md).*
