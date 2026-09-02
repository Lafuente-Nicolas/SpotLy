# Brouillon — Spotly

# 1. Présentation du projet

## Nom du projet
Spotly

## Slogan
Find what’s worth it, right now.

## Concept

Spotly est une application communautaire de micro-découvertes locales destinée aux voyageurs.

L’application permet de découvrir rapidement des lieux, activités et expériences autour de soi selon :
- la proximité,
- le temps disponible,
- les préférences utilisateur,
- les recommandations d’autres voyageurs.

L’objectif est d’aider les utilisateurs à répondre à la question :

“Qu’est-ce que je peux faire maintenant, ici, avec le temps que j’ai ?”

Chaque spot peut contenir :
- une durée estimée,
- une distance réelle,
- des photos authentiques,
- des retours d’expérience,
- des tags et catégories,
- des informations contextuelles utiles.

Spotly favorise une découverte spontanée, communautaire et éco-responsable du voyage.

---

# 2. Objectifs du projet

## Objectifs principaux
- Permettre aux voyageurs de trouver rapidement des activités proches.
- Adapter les recommandations selon le temps disponible.
- Favoriser les déplacements à pied ou en mobilité douce.
- Mettre en avant des recommandations communautaires fiables.
- Simplifier la découverte locale spontanée.
- Créer une communauté contributive et engagée.
- Valoriser les commerces et activités locales via une offre professionnelle.

---

# 3. Public cible

## Cibles principales
- Voyageurs solo
- Backpackers
- Touristes en court séjour
- Digital nomads
- Voyageurs longue durée

## Cibles secondaires
- Guides locaux
- Cafés et coworkings
- Restaurants
- Activités touristiques locales
- Organisateurs d’événements

---

# 4. Fonctionnalités principales

## 4.1 Gestion des utilisateurs

### Fonctionnalités
- Inscription
- Connexion / déconnexion
- Réinitialisation du mot de passe
- Vérification email
- Gestion du profil utilisateur
- Photo de profil
- Gestion des favoris
- Désactivation du compte
- Historique d’activité

### Préférences utilisateur
- aventure
- food
- culture
- nature
- détente
- coworking

---

## 4.2 Gestion des spots

### Création de spot
Chaque spot doit contenir :
- un titre,
- une description,
- une catégorie,
- une localisation GPS,
- une durée estimée,
- des tags,
- des photos.

### Durées disponibles
- 30 min
- 1h
- 2h
- demi-journée
- journée

### Catégories possibles
- café
- vue
- marché
- balade
- street food
- coworking
- rooftop
- randonnée
- plage
- sunset

### Informations complémentaires
- moment idéal,
- distance à pied,
- mini retour d’expérience,
- météo ou contexte conseillé.

---

## 4.3 Carte interactive

### Fonctionnalités
- Affichage des spots autour de l’utilisateur
- Géolocalisation
- Filtres dynamiques
- Clustering des spots proches
- Affichage par catégorie
- Affichage par popularité
- Affichage des favoris
- Chargement dynamique des spots

### Filtres disponibles
- catégorie,
- durée,
- proximité,
- popularité,
- tags,
- moment idéal.

---

## 4.4 Recherche

### Fonctionnalités
- Recherche textuelle
- Recherche par géolocalisation
- Recherche par filtres combinés
- Suggestions intelligentes

---

## 4.5 Interactions sociales

### Fonctionnalités
- Likes
- Commentaires
- Sauvegarde en favoris
- Partage de spots
- Signalement de contenu

### Fonctionnalités optionnelles
- Réponses aux commentaires
- Suivi d’utilisateurs

---

## 4.6 Notifications

### Notifications possibles
- Nouveau like
- Nouveau commentaire
- Spot validé
- Réponse professionnelle
- Événement proche

---

## 4.7 Administration

### Fonctionnalités administrateur
- Gestion des utilisateurs
- Gestion des spots
- Validation et modération des contenus
- Gestion des signalements
- Gestion des catégories
- Suspension de comptes
- Consultation des statistiques

---

# 5. Règles métier

## 5.1 Utilisateurs
- Un utilisateur doit être connecté pour publier un spot.
- Un utilisateur ne peut posséder qu’un seul compte par adresse email.
- L’adresse email doit être vérifiée à l’inscription.
- Un utilisateur peut modifier uniquement ses propres données.
- Un utilisateur peut supprimer uniquement ses propres contenus.
- Un utilisateur peut enregistrer des spots en favoris.
- Un utilisateur peut commenter un spot.
- Un utilisateur peut liker un spot une seule fois.
- Un utilisateur peut signaler un contenu.
- Un utilisateur suspendu ne peut plus publier de contenu.

---

## 5.2 Spots
- Chaque spot doit contenir :
  - un titre,
  - une description,
  - une catégorie,
  - une localisation,
  - une durée estimée.
- Un spot doit être associé à un utilisateur.
- Un spot peut contenir plusieurs photos.
- Un spot doit posséder des coordonnées GPS valides.
- Un spot peut être modifié uniquement par son créateur ou un administrateur.
- Un spot peut être supprimé uniquement par son créateur ou un administrateur.
- Un spot signalé plusieurs fois peut être masqué automatiquement.
- Un spot ne doit pas contenir de contenu offensant ou illégal.
- Un spot ne doit pas être publié en doublon.
- Un spot peut être archivé.

---

## 5.3 Carte interactive
- Les spots doivent être triés selon la distance.
- Les spots doivent être affichés dynamiquement selon la zone visible.
- Les spots proches doivent être regroupés automatiquement.
- Les spots supprimés ou archivés ne doivent plus apparaître publiquement.
- Les spots populaires peuvent être priorisés.
- La carte doit rester fluide sur mobile.

---

## 5.4 Commentaires
- Un commentaire doit être associé à un utilisateur et à un spot.
- Un commentaire offensant peut être supprimé.
- Les interactions doivent être limitées afin d’éviter le spam.
- Les commentaires peuvent être signalés.

---

## 5.5 Notifications
- Les notifications peuvent être activées ou désactivées.
- Un utilisateur reçoit des notifications selon ses interactions.

---

## 5.6 Administration
- Un administrateur peut supprimer un contenu.
- Un administrateur peut suspendre un utilisateur.
- Un administrateur peut consulter les signalements.
- Un administrateur peut masquer un contenu.
- Un administrateur peut gérer les catégories.

---

# 6. Modèle économique

## 6.1 Version gratuite

Les utilisateurs gratuits peuvent :
- consulter la carte,
- rechercher des spots,
- publier des spots,
- liker et commenter,
- enregistrer des favoris,
- filtrer les spots,
- consulter les profils publics.

---

## 6.2 Version Business / Pro

Les professionnels peuvent :
- publier des activités,
- afficher leurs coordonnées,
- ajouter un site web,
- ajouter Instagram,
- ajouter WhatsApp,
- proposer des réservations,
- publier davantage de médias,
- accéder à des statistiques.

### Exemples de professionnels
- guide local,
- surf school,
- coworking,
- rooftop,
- restaurant,
- excursion,
- plongée,
- spa,
- location de scooter.

---

## 6.3 Fonctionnalités Premium Pro
- Badge vérifié
- Mise en avant locale
- Galerie avancée
- Statistiques détaillées
- Événements temporaires
- Réponses officielles
- Réservation simplifiée

---

# 7. Contraintes techniques

## Frontend
- Responsive mobile-first
- Compatibilité tablette et desktop
- Interface légère et rapide

## Backend
- API sécurisée
- Validation serveur obligatoire
- Gestion des rôles utilisateurs

## Base de données
- Stockage des utilisateurs
- Stockage des spots
- Gestion des interactions
- Gestion des signalements

## Géolocalisation
- Autorisation utilisateur obligatoire
- Fallback si refus
- Protection de la vie privée

---

# 8. Éco-conception

## Optimisations prévues
- Compression automatique des images
- Lazy loading
- Pagination
- Mise en cache
- Réduction des appels API
- Chargement dynamique des données
- Utilisation de formats optimisés (WebP)
- Suppression des métadonnées EXIF
- Limitation des dépendances externes
- Interface sobre et légère
- Limitation des animations
- Mode sombre optionnel

---

# 9. Sécurité

## Authentification
- Mots de passe hashés
- Authentification sécurisée
- Sessions limitées dans le temps
- Protection brute force

## Protection applicative
- Protection SQL Injection
- Protection XSS
- Validation backend obligatoire
- Vérification des fichiers uploadés
- Protection anti-spam
- CAPTCHA à l’inscription

## Vie privée / RGPD
- Consentement cookies
- Suppression des données utilisateur
- Export des données
- Protection de la localisation
- Respect du RGPD

---

# 10. Workflow des spots

## États possibles
- brouillon,
- publié,
- signalé,
- masqué,
- archivé,
- supprimé.

---

# 11. Accessibilité

L’application doit respecter les principes d’accessibilité :
- responsive mobile,
- contraste suffisant,
- navigation clavier,
- tailles de police lisibles,
- textes alternatifs pour images.

---

# 12. Gestion des performances

## Optimisations prévues
- lazy loading,
- pagination,
- cache,
- compression des médias,
- optimisation des requêtes API,
- chargement conditionnel des données.

---

# 13. MVP (Version minimale viable)

## Fonctionnalités MVP

### Utilisateurs
- inscription,
- connexion,
- profil utilisateur.

### Spots
- création de spots,
- ajout photo,
- catégories,
- durée,
- géolocalisation.

### Carte
- carte interactive,
- affichage des spots proches,
- filtres.

### Social
- likes,
- favoris,
- commentaires simples.

### Administration
- modération basique.

---

# 14. Roadmap / Évolutions futures

## Évolutions possibles
- application mobile native,
- traduction automatique,
- recommandations par IA,
- réservation intégrée,
- événements temporaires avancés,
- gamification avancée,
- mode hors ligne,
- notifications géolocalisées,
- collections publiques,
- recommandations personnalisées en temps réel.

---

# Architecture technique conseillée

## Frontend
- React
- Vite
- TypeScript
- Tailwind CSS
- MapLibre GL JS

## Backend
- Node.js
- Express

## Base de données
- PostgreSQL
- Prisma

## Services externes
- Cloudinary

---

# Palette de couleurs

| Couleur | Code HEX | Utilisation |
|---|---|---|
| Deep Teal | #0F4C5C | Navbar, UI map |
| Sunset Coral | #FF7F50 | CTA, likes |
| Sand Beige | #F5F1E8 | Fond général |
| Charcoal | #1E1E1E | Textes, dark mode |
| Sage Green | #7A9E7E | Tags, badges |

---

# Typographies

| Élément | Police | Style |
|---|---|---|
| Titres | Inter SemiBold / Bold | Moderne |
| Texte | Inter Regular | Lisible mobile |
| Boutons | Inter Medium | Compact |
| Tags / badges | Inter Medium | UI moderne |

---

# Icônes et illustrations

## Style visuel
- minimaliste,
- moderne,
- mobile-first,
- épuré.

## Bibliothèque d’icônes
- Lucide Icons

---

# Ambiance visuelle choisie

L’ambiance visuelle de Spotly repose sur un style moderne, minimaliste et mobile-first inspiré des applications de voyage et de cartographie modernes.

L’interface privilégie :
- la simplicité,
- la lisibilité,
- les animations légères,
- une navigation rapide sur mobile.

La carte interactive constitue l’élément central de l’application avec :
- un affichage moderne,
- des markers personnalisés,
- du clustering dynamique,
- un mode sombre,
- une expérience fluide et immersive.