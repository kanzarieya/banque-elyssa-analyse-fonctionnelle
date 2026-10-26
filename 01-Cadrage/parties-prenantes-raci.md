# Carte des parties prenantes — Projet Banque Elyssa

**Auteur :** Eya Kanzari (analyste fonctionnelle)

## 1. Matrice pouvoir / intérêt

```
Intérêt élevé │  RISQUES (satisfaire)      │   ACTEURS CLÉS (gérer de près)
              │  · Agent d'accueil         │   · Directrice digitalisation (sponsor)
              │  · Analyste crédit        │   · Responsable des risques
              │                            │   · Directeur d'agence
Intérêt faible│  CROWD (informer)          │   CONTEXTE (tenir informé)
              │  · Comité de crédit       │   · Clients (via portail + enquête)
              │  · DSI externe            │
              └────────────────────────────┴──────────────────────────
                 Pouvoir faible               Pouvoir élevé
```

**Stratégie par quadrant :**

- **Acteurs clés** (sponsor, risques, directeur d'agence) : implication active — revues
  hebdomadaires de livrables, validation des arbitrages.
- **Risques** (agent d'accueil, analyste crédit) : utilisateurs finaux — les écouter tôt
  et souvent via les entretiens d'élicitation, sinon ils feront échouer l'adoption.
- **Contexte** (clients) : informés par le portail de suivi et une enquête de satisfaction.
- **Crowd** (comité, DSI) : informés par la note de synthèse finale.

## 2. Fiches des parties prenantes

| Partie prenante | Rôle dans le projet | Attentes | Craintes | Implication | Communication |
|---|---|---|---|---|---|
| **Mme Nadia Jelassi** — Directrice de la digitalisation | Sponsor, arbitre des priorités | Un dossier complet et argumenté pour lancer le projet réel | Dépassement de budget, projet sans fin | Forte | Point hebdo de 30 min (revue de livrable) |
| **M. Hichem Mansouri** — Directeur d'agence Centre-ville | Expert métier, porteur des besoins terrain | Moins de files d'attente, moins d'appels de suivi | Que le digital exclue les clients peu à l'aise avec le web | Forte | Entretien S2 + revue AS-IS |
| **Mme Selma Bouzid** — Responsable des risques | Experte conformité et scoring | Traçabilité complète, règles de décision respectées | Perte de contrôle sur l'étude, décisions automatisées opaques | Forte | Entretien S2 + revue BRD |
| **M. Karim Gharbi** — Analyste crédit (siège) | Utilisateur clé du futur outil | Dossiers complets dès l'arrivée, fin des re-saisies | Outil lent, double saisie déguisée | Forte | Entretien S2 + revue user stories |
| **Mme Amira Trabelsi** — Agent d'accueil | Utilisatrice finale | Formulaires clairs, moins de paperasse | Être jugée sur de nouveaux indicateurs, formation insuffisante | Moyenne | Entretien S2 + test des wireframes S5 |
| **Sami Ben Ammar** — Client, gérant de micro-entreprise | Voix des clients | Déposer sans se déplacer, suivre l'avancement | Rejet silencieux, démarches invisibles | Moyenne | Entretien simulé + enquête finale fictive |

## 3. Matrice RACI

Légende : **R** = Réalise · **A** = Approuve (responsable final) · **C** = Consulté · **I** = Informé

| Activité | Eya Kanzari (analyste BA) | N. Jelassi (sponsor) | Experts métier (agence + siège) | Clients |
|---|---|---|---|---|
| Cadrage et périmètre | R | A | C | I |
| Élicitation (entretiens) | R | I | C (interviewés) | C (interviewé) |
| Cartographie AS-IS | R | A | C | I |
| BRD | R | A | C | I |
| User stories + backlog | R | A | C | I |
| Modélisation TO-BE | R | A | C | I |
| Wireframes | R | I | C (validation ergonomie) | C |
| Business case | R | A | I | I |
| Recette / validation finale | R | A | C | I |

## 4. Gestion des attentes — trois points sensibles identifiés dès le cadrage

1. **Le digital ne doit pas exclure le canal agence** : les clients habitués au papier
   doivent toujours pouvoir déposer en agence (directeur d'agence).
2. **La décision de crédit reste humaine** : l'outil prépare et trace, le comité décide
   (responsable des risques).
3. **Pas de surveillance déguisée** : les nouveaux indicateurs servent à fluidifier,
   pas à noter les agents (agent d'accueil).
