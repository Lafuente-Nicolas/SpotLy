# Cahier des charges — Spotly

# 1. Présentation du projet

## 1.1 Nom du projet

**Spotly**

## 1.2 Slogan

**Find what’s worth it, right now.**

## 1.3 Concept

Spotly est une application communautaire de **micro-découvertes locales destinée aux voyageurs**.

L’application a pour objectif de permettre aux utilisateurs de découvrir rapidement des lieux, activités et expériences intéressantes autour d’eux, en tenant compte de plusieurs critères :

- la proximité ;
- le temps disponible ;
- les préférences de l’utilisateur ;
- les recommandations et retours d’expérience de la communauté.

Spotly s’adresse principalement aux voyageurs qui souhaitent découvrir une destination de manière **spontanée et locale**, sans nécessairement avoir planifié leurs activités à l’avance.

L'application repose sur un système de **spots**. Un spot correspond à un lieu, une activité ou une expérience pouvant être découverte par les utilisateurs. Il peut notamment être associé à une localisation, une durée estimée, des photos, une catégorie, des tags et un retour d’expérience.

L’objectif de Spotly est de proposer une expérience de découverte simple et rapide, permettant à l’utilisateur de répondre à une question centrale :

> **« Qu’est-ce que je peux faire maintenant, ici, avec le temps que j’ai ? »**

L’application s’appuie également sur une approche communautaire : les utilisateurs peuvent créer et partager leurs propres spots, mais aussi interagir avec les découvertes des autres membres grâce aux likes, commentaires et favoris.

Spotly cherche enfin à favoriser une découverte locale et plus responsable du voyage, notamment en mettant en avant les expériences accessibles à proximité et les déplacements à pied ou en mobilité douce lorsque cela est pertinent.

# 2. Expression du besoin

## 2.1 Contexte

Lorsqu’un voyageur découvre une nouvelle destination, il peut avoir envie de profiter de son temps libre pour découvrir les environs, sans forcément avoir prévu une activité à l’avance. Il peut notamment disposer d’un temps limité entre deux activités, rechercher une expérience à proximité ou simplement vouloir découvrir un lieu intéressant autour de lui.

Les solutions existantes permettent généralement de rechercher des lieux, des activités ou des points d’intérêt, mais elles peuvent proposer un volume important de résultats et nécessiter plusieurs recherches ou comparaisons avant de trouver une activité réellement adaptée à la situation du voyageur.

Spotly part de ce constat et cherche à simplifier cette découverte en mettant l’accent sur les expériences locales et spontanées.

## 2.2 Problématique

**Comment permettre à un voyageur de trouver rapidement une activité ou une expérience locale pertinente, à proximité de sa position et adaptée au temps dont il dispose ?**

Cette problématique concerne particulièrement les voyageurs qui souhaitent découvrir une destination de manière spontanée, notamment les voyageurs solo, backpackers, touristes en court séjour et digital nomads.

## 2.3 Besoin identifié

Le besoin principal est de pouvoir **identifier rapidement quoi faire autour de soi**, sans devoir parcourir de nombreuses informations ou utiliser plusieurs services différents.

Pour cela, le voyageur doit pouvoir prendre en compte plusieurs critères :

- sa localisation ;
- la distance à parcourir ;
- le temps dont il dispose ;
- ses centres d’intérêt ;
- les recommandations d’autres utilisateurs ;
- le contexte de l’expérience, comme le moment idéal pour la réaliser.

L’objectif n’est donc pas uniquement de proposer une liste de lieux, mais de permettre à l’utilisateur de trouver une expérience correspondant à **sa situation actuelle**.

## 2.4 Réponse apportée par Spotly

Spotly est une application communautaire de micro-découvertes locales destinée aux voyageurs.

L’application permet de découvrir des lieux, activités et expériences autour de soi en combinant notamment la proximité, le temps disponible et les préférences de l’utilisateur.

Les expériences sont proposées sous la forme de **spots** créés et enrichis par la communauté. Chaque spot peut notamment contenir une localisation, une durée estimée, des photos, une catégorie, des tags et un retour d’expérience.

L’utilisateur peut ainsi consulter les spots proches de lui sur une carte interactive et utiliser différents filtres afin de réduire les résultats et identifier plus rapidement une expérience correspondant à ses besoins.

Spotly cherche également à favoriser la découverte locale et les déplacements à pied ou en mobilité douce lorsque cela est pertinent.

## 2.5 Valeur apportée par l'application

La principale valeur de Spotly repose sur la **mise en relation entre une situation donnée et une expérience locale pertinente**.

Plutôt que de demander à l’utilisateur de rechercher lui-même une activité parmi un grand nombre de résultats, Spotly cherche à lui permettre de partir de sa situation :

> **« Qu’est-ce que je peux faire maintenant, ici, avec le temps que j’ai ? »**

L’application transforme ainsi une recherche générale d’activités en une découverte contextualisée, rapide et communautaire.

## 2.6 Fonctionnalité principale

### Découverte contextualisée de spots

La fonctionnalité principale de Spotly est la possibilité de **découvrir des spots autour de soi en fonction de sa localisation et du temps disponible**.

L’utilisateur peut :

1. autoriser l’application à accéder à sa localisation ;
2. consulter les spots disponibles autour de lui ;
3. indiquer ou sélectionner le temps dont il dispose ;
4. filtrer les résultats selon ses préférences ;
5. consulter les informations d’un spot ;
6. choisir l’expérience qui correspond le mieux à sa situation.

Cette fonctionnalité constitue le cœur de Spotly, car elle répond directement à la problématique identifiée : **aider un voyageur à décider rapidement quoi faire, où il se trouve et avec le temps dont il dispose.**

# 3. Cahier des charges fonctionnel

## 3.1 Fonctionnalité principale : découverte contextualisée

La fonctionnalité centrale de Spotly est de permettre à un voyageur de **découvrir des expériences locales adaptées à sa situation**, notamment en fonction de sa localisation et du temps dont il dispose.

Le parcours principal est le suivant :

1. L'utilisateur ouvre Spotly et autorise l'accès à sa localisation.
2. L'application identifie les spots disponibles autour de lui.
3. L'utilisateur indique ou sélectionne le temps dont il dispose.
4. Il peut affiner les résultats grâce à différents critères : catégorie, distance, tags, popularité ou préférences.
5. Spotly affiche les résultats correspondants sur la carte.
6. L'utilisateur sélectionne un spot afin de consulter ses informations.
7. Il peut ensuite enregistrer le spot en favori, consulter les retours de la communauté ou s'y rendre.

**Valeur fonctionnelle :** cette fonctionnalité permet de réduire le temps nécessaire à la recherche d'une activité et aide l'utilisateur à prendre une décision rapidement, en fonction de sa situation réelle.

## 3.2 Gestion des spots

Les utilisateurs authentifiés peuvent créer des spots afin de partager leurs découvertes avec la communauté.

Un spot doit notamment comporter :

- un titre ;
- une description ;
- une catégorie ;
- une localisation GPS ;
- une durée estimée ;
- des tags ;
- une ou plusieurs photos.

Les durées proposées sont notamment :

- 30 minutes ;
- 1 heure ;
- 2 heures ;
- demi-journée ;
- journée.

Un spot peut également contenir des informations complémentaires telles que le moment idéal pour le découvrir, la distance à pied ou un retour d'expérience.

Le créateur peut modifier ou supprimer ses propres spots. Les administrateurs disposent également de droits de modification, suppression et modération.

## 3.3 Carte interactive et géolocalisation

La carte constitue le principal moyen de visualisation des spots.

Elle permet notamment :

- d'afficher les spots autour de l'utilisateur ;
- d'utiliser sa position géographique ;
- d'afficher les spots selon la zone visible ;
- de regrouper les spots proches grâce au clustering ;
- de filtrer les spots ;
- d'afficher les favoris ;
- de charger dynamiquement les données.

L'application doit demander l'autorisation d'utiliser la géolocalisation. En cas de refus, un fonctionnement alternatif doit être proposé.

## 3.4 Recherche et filtres

L'utilisateur peut rechercher des spots de différentes manières :

- recherche textuelle ;
- recherche autour d'une localisation ;
- combinaison de plusieurs filtres.

Les principaux filtres sont :

- catégorie ;
- durée ;
- proximité ;
- popularité ;
- tags ;
- moment idéal.

Cette fonctionnalité permet de compléter la découverte automatique en donnant davantage de contrôle à l'utilisateur.

## 3.5 Gestion du compte utilisateur

L'application permet à l'utilisateur de :

- créer un compte ;
- se connecter et se déconnecter ;
- réinitialiser son mot de passe ;
- vérifier son adresse email ;
- gérer son profil ;
- ajouter une photo de profil ;
- gérer ses favoris ;
- consulter son historique ;
- désactiver son compte.

L'utilisateur peut également renseigner des préférences telles que **aventure, food, culture, nature, détente ou coworking** afin de personnaliser son expérience.

## 3.6 Interactions communautaires

Spotly repose sur une dimension communautaire permettant aux utilisateurs d'interagir avec les spots.

Les utilisateurs peuvent :

- liker un spot ;
- commenter ;
- ajouter un spot à leurs favoris ;
- partager un spot ;
- signaler un contenu.

Un utilisateur ne peut liker un même spot qu'une seule fois et les interactions doivent être limitées afin de réduire les risques de spam.

## 3.7 Administration et modération

Une interface d'administration permet de garantir la qualité et la sécurité des contenus publiés.

L'administrateur peut notamment :

- gérer les utilisateurs ;
- gérer les spots ;
- modérer les contenus ;
- consulter les signalements ;
- gérer les catégories ;
- suspendre des comptes ;
- masquer ou supprimer du contenu ;
- consulter des statistiques.

Les utilisateurs suspendus ne peuvent plus publier de contenu.

## 3.8 Notifications

Le système peut informer les utilisateurs de différentes actions liées à leur compte ou à leurs contenus :

- nouveau like ;
- nouveau commentaire ;
- validation d'un spot ;
- réponse d'un professionnel ;
- événement à proximité.

Les notifications peuvent être activées ou désactivées par l'utilisateur.

## 3.9 MVP

Pour la première version de Spotly, le périmètre fonctionnel est volontairement limité afin de se concentrer sur la proposition de valeur principale.

### Fonctionnalités utilisateurs

- inscription ;
- connexion ;
- profil.

### Fonctionnalités spots

- création ;
- ajout de photos ;
- catégories ;
- durée ;
- géolocalisation.

### Fonctionnalités de découverte

- carte interactive ;
- affichage des spots proches ;
- filtres.

### Fonctionnalités communautaires

- likes ;
- favoris ;
- commentaires simples.

### Administration

- modération basique.
