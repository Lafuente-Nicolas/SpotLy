# Spotly

> **Find what's worth it, right now.**

Spotly est une application web communautaire de découverte locale destinée aux voyageurs. Elle aide à répondre à une question simple :

> **« Qu'est-ce que je peux faire maintenant, ici, avec le temps que j'ai ? »**

Projet réalisé dans le cadre du titre professionnel **Concepteur Développeur d'Applications (CDA)**, avec une spécialisation en **éco-conception**.

---

## État du projet

Le projet est en **phase de conception**. Les spécifications fonctionnelles, les cas d'utilisation et le backlog sont rédigés. La modélisation des données et le développement n'ont pas encore commencé.

---

## Le concept

Spotly repose sur des **spots** : des lieux, activités ou expériences locales proposés par la communauté. Un point de vue pour le coucher du soleil, un café calme pour travailler, un marché local, une balade courte…

Chaque spot indique notamment sa localisation, sa **durée estimée**, sa catégorie, des tags et des photos. En croisant la **position** de l'utilisateur, son **temps disponible** et la durée des spots, Spotly ne propose que des expériences réellement réalisables.

Spotly n'est donc pas un annuaire de lieux touristiques : c'est un outil de **découverte contextualisée**, pensé pour décider vite.

### Public cible

Voyageurs solo, backpackers, touristes en court séjour, digital nomads et voyageurs longue durée. Les profils détaillés sont décrits dans les [personas](docs/personna.md).

---

## Périmètre du MVP

Le MVP comprend **12 User Stories**, détaillées avec leurs critères d'acceptation dans le [backlog](docs/backlog.md).

| Domaine | Fonctionnalités |
| --- | --- |
| **Compte** | Créer un compte, se connecter, se déconnecter |
| **Découverte** | Carte des spots, recherche par mot-clé ou par zone, filtres, **temps disponible** |
| **Spots** | Consulter un spot, ajouter un spot, modifier ou supprimer ses spots |
| **Favoris** | Ajouter un spot à ses favoris, consulter ses favoris |
| **Modération** | Masquer un spot (administrateur) |

L'utilisation de Spotly nécessite un compte. Les choix qui définissent ce périmètre sont expliqués dans les [décisions de conception](docs/decisions-de-conception.md).

---

## Vision et évolutions

Après le MVP, plusieurs évolutions sont prévues ou envisagées :

- **Communauté** : commentaires, notes de 1 à 5, signalement de contenus, profil utilisateur, traitement des signalements.
- **Compte** : vérification de l'adresse e-mail, réinitialisation du mot de passe, préférences (aventure, food, culture, nature, détente, coworking).
- **Découverte** : prise en compte du temps de trajet à pied, moment idéal, tri par popularité.
- **Modération** : suspension de comptes, gestion des catégories depuis l'interface.
- **Offre professionnelle** : comptes pour les guides, cafés, coworkings, écoles de surf ou restaurants, avec coordonnées, liens, réservation, mise en avant locale et statistiques.
- **À plus long terme** : notifications, événements à proximité, mode hors ligne, application mobile.

Ces évolutions ne font pas partie du MVP.

---

## Choix techniques

| Domaine | Technologie |
| --- | --- |
| Interface | React, TypeScript, Vite |
| Styles | Tailwind CSS |
| Cartographie | MapLibre GL JS |
| API | Node.js, Express (API REST) |
| Base de données | PostgreSQL, Prisma |
| Médias | Cloudinary |

Les choix et les versions sont justifiés dans le [cahier des charges technique](docs/Brouillon-cahier-des-charges-tech.md), en cours de rédaction.

---

## Éco-conception

L'éco-conception guide les choix techniques et doit être démontrée par des mesures. Les principaux leviers identifiés sont :

- le poids des images : compression, format WebP, tailles adaptées, 5 photos maximum par spot ;
- le chargement des seuls spots de la zone visible de la carte, avec regroupement des marqueurs ;
- la limitation des requêtes réseau et la pagination ;
- la sobriété fonctionnelle et la limitation des dépendances.

Voir la [démarche d'éco-conception](docs/démarche-éco-conception.md), le [contexte de l'analyse](eco/context.md) et l'[analyse des impacts](eco/analyse-des-impacts.md).

---

## Sécurité et données personnelles

- Mots de passe hachés, sessions limitées dans le temps, limitation des tentatives de connexion.
- Validation de toutes les données par l'API, même si elles sont déjà contrôlées dans l'interface.
- Droits vérifiés côté serveur : un utilisateur ne modifie que ses propres contenus, la modération est réservée aux administrateurs.
- Protection des données de localisation et collecte limitée aux données nécessaires.

---

## Identité visuelle

Une interface moderne, minimaliste et **mobile-first**, où la carte reste l'élément principal.

| Couleur | Code | Usage |
| --- | --- | --- |
| Deep Teal | `#0F4C5C` | Navigation, éléments principaux |
| Sunset Coral | `#FF7F50` | Actions importantes |
| Sand Beige | `#F5F1E8` | Fond, selon les écrans |
| Charcoal | `#1E1E1E` | Texte, interface sombre |
| Sage Green | `#7A9E7E` | Tags, éléments secondaires |

- **Typographie** : Inter (SemiBold ou Bold pour les titres, Regular pour le texte, Medium pour les boutons et les tags).
- **Icônes** : Lucide.

---

## Documentation

### Analyse du besoin

- [Présentation du projet](docs/presentation-du-projet.md)
- [Expression du besoin](docs/expression-du-besoin.md)
- [Personas](docs/personna.md)

### Spécifications fonctionnelles

- [Contraintes et livrables](docs/3.1_Contraintes_et_Livrables.md)
- [Acteurs et rôles](<docs/3.2_Acteurs_&_roles.md>)
- [Cas d'utilisation](<docs/3.3_Cas_d'utilisation.md>)
- [Parcours utilisateurs et scénarios](<docs/3.4_Parcours_utilisateurs_&_scénarios.md>)
- [User Journeys](docs/Journey.md)
- [Cahier des charges fonctionnel](docs/cahier-des-charges-fonctionnel.md)

### Organisation et décisions

- [Backlog](docs/backlog.md) — suivi dans Trello
- [Décisions de conception](docs/decisions-de-conception.md)

### Technique et éco-conception

- [Cahier des charges technique](docs/Brouillon-cahier-des-charges-tech.md) *(brouillon)*
- [Démarche d'éco-conception](docs/démarche-éco-conception.md)
- [Contexte de l'analyse d'éco-conception](eco/context.md)
- [Analyse des impacts](eco/analyse-des-impacts.md)
