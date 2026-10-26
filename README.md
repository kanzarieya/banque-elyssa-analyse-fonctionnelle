# Projet Banque Elyssa — Digitalisation du processus de demande de crédit

**Portfolio d'analyse fonctionnelle — Eya Kanzari**
Cas d'école réalisé en autonomie

> **Transparence :** la « Banque Elyssa » est une entreprise **fictive**. Tous les chiffres,
> entretiens et verbatims sont des **hypothèses réalistes documentées**, utilisées pour
> simuler une mission d'analyse fonctionnelle complète dans un but de démonstration.
> Ce projet a été mené seule, de bout en bout, avec les méthodes et outils d'un vrai
> projet d'analyse.

## Contexte en une phrase

Une banque commerciale tunisienne (fictive) traite ses demandes de crédit sur papier :
délai moyen de 12 jours, 35 % de dossiers incomplets, client sans aucune visibilité.
Ma mission : produire le dossier d'analyse complet d'un parcours digitalisé.

## Structure du dépôt

```
Projet-Banque-Elyssa/
├── README.md              cette page : fil conducteur, résultats, contact
├── 01-Cadrage/            note de cadrage · parties prenantes (RACI)
├── 02-Elicitation/        personas · guides d'entretien · 17 constats
├── 03-Analyse/            AS-IS en BPMN · matrice des douleurs · causes racines · BRD
├── 04-Exigences/          14 user stories (Gherkin) · backlog MoSCoW en 4 sprints
├── 05-Solution/           TO-BE en BPMN · 12 maquettes desktop · version interactive
└── 06-Restitution/        business case chiffré · matrice de traçabilité
```

Chaque dossier contient un `README.md` qui annonce **la question traitée** et le fichier à lire
en premier. Le fil conducteur va dans un seul sens : constat → douleur → cause racine → exigence
→ user story → écran → valeur.

## Contenu du portfolio

| Dossier | Livrable | Étape |
|---|---|---|
| [`01-Cadrage/`](01-Cadrage/README.md) | [Note de cadrage](01-Cadrage/note-de-cadrage.md), [parties prenantes et RACI](01-Cadrage/parties-prenantes-raci.md) | S1 |
| [`02-Elicitation/`](02-Elicitation/README.md) | [Personas](02-Elicitation/personas.md), [guides d'entretien](02-Elicitation/guides-dentretien.md), [synthèse des 17 constats](02-Elicitation/synthese-constats.md) | S2 |
| [`03-Analyse/`](03-Analyse/README.md) | [AS-IS en BPMN](03-Analyse/as-is-processus.md), [matrice des douleurs](03-Analyse/matrice-douleurs.md), [causes racines](03-Analyse/causes-racines.md), [BRD](03-Analyse/BRD.md) | S3 |
| [`04-Exigences/`](04-Exigences/README.md) | [User stories, critères Gherkin et backlog MoSCoW](04-Exigences/user-stories-backlog.md) | S4 |
| [`05-Solution/`](05-Solution/README.md) | [TO-BE en BPMN](05-Solution/to-be-processus.md), [maquettes desktop couleur — 12 écrans](05-Solution/wireframes/README.md) | S5 |
| [`06-Restitution/`](06-Restitution/README.md) | [Business case chiffré](06-Restitution/business-case.md), [matrice de traçabilité](06-Restitution/matrice-tracabilite.md) | S6 |

## Outils utilisés

Bizagi Modeler (BPMN) · HTML/CSS (maquettes desktop couleur, version interactive : [`wireframes.html`](05-Solution/wireframes.html)) · Jira (backlog) 
## Résultats clés (cibles du processus cible)

- Délai moyen de traitement : **12 jours → 5 jours ouvrés**
- Dossiers incomplets : **35 % → ≤ 10 %**
- Saisies du même dossier : **3 → 1**
- Notifications automatiques au client : **0 % → 100 %**

---

*ek.kanzari@gmail.com · [linkedin.com/in/eya-kanzari-43a41822a](https://www.linkedin.com/in/eya-kanzari-43a41822a)*
