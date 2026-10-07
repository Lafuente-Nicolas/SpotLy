# Gestion du backlog — Spotly

## 1. Objectif

Le backlog de Spotly permet de recenser et de prioriser les fonctionnalités nécessaires au développement de l'application.

Chaque fonctionnalité est représentée sous la forme d'une **User Story**, afin de se concentrer sur le besoin de l'utilisateur et la valeur apportée par la fonctionnalité.

Le suivi du projet est réalisé avec **Trello**, sous la forme d'un tableau Kanban.

### Organisation du tableau

- **Backlog** : fonctionnalités identifiées mais pas encore planifiées.
- **À faire** : fonctionnalités sélectionnées pour être développées.
- **En cours** : fonctionnalités actuellement développées.
- **En test** : fonctionnalités développées en cours de vérification.
- **Terminé** : fonctionnalités validées.

---

## 2. Organisation des fonctionnalités

Les User Stories sont regroupées en **6 Epics** représentant les principaux domaines fonctionnels de Spotly.

| Epic | Description |
|---|---|
| Authentification | Gestion des comptes et de la connexion |
| Découverte | Recherche et découverte des spots |
| Gestion des spots | Consultation et ajout de spots |
| Interactions | Favoris, commentaires, notes et signalements |
| Profil utilisateur | Consultation et modification du profil |
| Administration | Gestion des signalements et de la qualité des contenus |

---

## 3. User Stories

## Epic 1 — Authentification

### US-01 — Créer un compte

> En tant que visiteur, je souhaite créer un compte Spotly, afin de pouvoir enregistrer mes spots favoris et contribuer à la communauté.

**Priorité : P1 — MVP**

### US-02 — Se connecter

> En tant qu'utilisateur, je souhaite me connecter à mon compte, afin de retrouver mes favoris et mes contributions.

**Priorité : P1 — MVP**

---

## Epic 2 — Découverte

### US-03 — Voir les spots sur une carte

> En tant qu'utilisateur, je souhaite voir les spots autour de moi sur une carte, afin de découvrir rapidement les lieux intéressants à proximité.

**Priorité : P1 — MVP**

### US-04 — Rechercher un spot

> En tant qu'utilisateur, je souhaite rechercher un lieu ou une activité, afin de trouver rapidement un spot correspondant à mon besoin.

**Priorité : P1 — MVP**

### US-05 — Filtrer les spots

> En tant qu'utilisateur, je souhaite filtrer les spots par catégorie, afin d'afficher uniquement les lieux qui m'intéressent.

**Priorité : P1 — MVP**

---

## Epic 3 — Gestion des spots

### US-06 — Consulter un spot

> En tant qu'utilisateur, je souhaite consulter les informations détaillées d'un spot, afin de savoir si ce lieu correspond à ce que je recherche.

**Priorité : P1 — MVP**

### US-07 — Ajouter un spot

> En tant qu'utilisateur connecté, je souhaite proposer un nouveau spot, afin de partager un lieu intéressant avec la communauté.

**Priorité : P1 — MVP**

---

## Epic 4 — Interactions

### US-08 — Ajouter un spot aux favoris

> En tant qu'utilisateur connecté, je souhaite enregistrer un spot dans mes favoris, afin de pouvoir le retrouver facilement plus tard.

**Priorité : P1 — MVP**

### US-09 — Consulter ses favoris

> En tant qu'utilisateur connecté, je souhaite consulter mes spots favoris, afin de retrouver facilement les lieux que j'ai enregistrés.

**Priorité : P1 — MVP**

### US-10 — Commenter un spot

> En tant qu'utilisateur connecté, je souhaite publier un commentaire sur un spot, afin de partager mon expérience avec les autres utilisateurs.

**Priorité : P2**

### US-11 — Noter un spot

> En tant qu'utilisateur connecté, je souhaite attribuer une note à un spot, afin d'aider les autres utilisateurs à évaluer sa qualité.

**Priorité : P2**

### US-12 — Signaler un contenu

> En tant qu'utilisateur, je souhaite signaler un contenu inapproprié ou incorrect, afin de contribuer à la qualité des informations présentes sur Spotly.

**Priorité : P2**

---

## Epic 5 — Profil utilisateur

### US-13 — Consulter son profil

> En tant qu'utilisateur connecté, je souhaite consulter mon profil, afin de retrouver mes informations et mes contributions sur Spotly.

**Priorité : P2**

### US-14 — Modifier son profil

> En tant qu'utilisateur connecté, je souhaite modifier mes informations personnelles, afin de garder mon profil à jour.

**Priorité : P3**

---

## Epic 6 — Administration

### US-15 — Traiter les signalements

> En tant qu'administrateur, je souhaite consulter les signalements, afin de maintenir la qualité des contenus de Spotly.

**Priorité : P3**

---

## 4. Priorisation

### P1 — MVP

- US-01 — Créer un compte
- US-02 — Se connecter
- US-03 — Voir les spots sur une carte
- US-04 — Rechercher un spot
- US-05 — Filtrer les spots
- US-06 — Consulter un spot
- US-07 — Ajouter un spot
- US-08 — Ajouter un spot aux favoris
- US-09 — Consulter ses favoris

### P2 — Évolutions

- US-10 — Commenter un spot
- US-11 — Noter un spot
- US-12 — Signaler un contenu
- US-13 — Consulter son profil

### P3 — Fonctionnalités secondaires

- US-14 — Modifier son profil
- US-15 — Traiter les signalements

---

## 5. Définition du MVP

Le **MVP (Minimum Viable Product)** de Spotly a pour objectif de proposer la fonctionnalité principale de l'application :

> **Permettre à un utilisateur de découvrir des spots autour de lui, de consulter leurs informations et de sauvegarder ceux qui l'intéressent.**

Le MVP se concentre donc sur la **découverte de lieux** et la **gestion des favoris**.

Les fonctionnalités communautaires et administratives pourront être ajoutées progressivement après validation du fonctionnement principal de l'application.

---

## 6. Suivi des User Stories

Chaque User Story est représentée par une **carte Trello**.

Une carte contient notamment :

- Identifiant de la User Story
- Titre
- Epic associé
- Description de la User Story
- Priorité
- Critères d'acceptation
- Statut
- Tâches techniques associées

### Exemple : US-03 — Voir les spots sur une carte

Tâches techniques possibles :

- Installer et configurer MapLibre GL JS
- Créer le composant de carte
- Récupérer les spots depuis l'API
- Afficher les marqueurs
- Afficher les informations d'un spot
- Ajouter la géolocalisation
- Tester l'affichage sur mobile

Cela permet de conserver une distinction entre **le besoin utilisateur (User Story)** et **la réalisation technique**.

---

## 7. Justification de la priorisation

La priorité est donnée aux fonctionnalités permettant de réaliser la proposition de valeur principale de Spotly.

La **carte, la recherche, les filtres et la consultation des spots** sont donc prioritaires car elles permettent directement à l'utilisateur de découvrir des lieux.

Les **favoris** sont également intégrés au MVP car ils permettent à l'utilisateur de conserver les spots qui l'intéressent.

Les commentaires, notes et signalements sont placés en P2 car ils améliorent l'aspect communautaire mais ne sont pas indispensables pour permettre la découverte des spots.

Enfin, les fonctionnalités d'administration et certaines fonctionnalités de profil sont placées en P3 car elles peuvent être développées après la mise en place du fonctionnement principal de l'application.

---

## 8. Outils utilisés

- **Trello** : gestion du backlog et suivi Kanban
- **Figma** : wireframes, maquettes et prototype
- **Git/GitHub** : gestion du code source et des versions

Cette organisation permet de passer progressivement de la **conception UX/UI** au **développement**, tout en gardant une vision claire des fonctionnalités à réaliser.
