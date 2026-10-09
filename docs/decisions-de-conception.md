# Décisions de conception — Spotly

Ce document consigne les décisions prises pour lever les incohérences entre les documents du projet (README, cahier des charges fonctionnel, backlog, cas d'utilisation). Il fait référence : en cas de contradiction, **c'est ce document qui s'applique**, et les autres documents doivent être alignés sur lui.

*Décisions validées le 9 octobre 2026.*

---

## D1 — Périmètre du MVP

**Décision :** le MVP correspond au backlog P1 (US-01 à US-09), complété par trois User Stories :

| US | Intitulé | Priorité |
|---|---|---|
| US-16 | Indiquer son temps disponible pour obtenir des spots compatibles | P1 — MVP |
| US-17 | Masquer un spot (administrateur) | P1 — MVP |
| US-18 | Gérer ses spots : modifier ou supprimer ses propres spots | P1 — MVP |

**Justification :**

- Le temps disponible est l'élément différenciant de Spotly. Il figure dans la problématique, les parcours et le diagramme UML, mais n'avait aucune User Story : il doit apparaître explicitement dans le MVP.
- Les spots étant publiés immédiatement, leur auteur doit pouvoir corriger une erreur (durée, position…) qui fausserait les résultats. US-18 a été ajoutée après la mise à jour des cas d'utilisation, qui prévoyaient ce cas sans User Story.
- La création de spots par la communauté fait partie du MVP. Il faut donc un moyen minimal de retirer un contenu problématique dès la première version, sans attendre le traitement complet des signalements (US-15, P3).

**Conséquence :** le MVP décrit dans le README (§13) et dans le cahier des charges fonctionnel (§3.9), qui incluait profil, likes, commentaires et modération, est remplacé par celui-ci.

---

## D2 — Appréciation des spots : notes, pas de likes

**Décision :** l'appréciation d'un spot se fait par une **note**, distincte du commentaire. Un utilisateur ne peut attribuer **qu'une seule note par spot** (il peut la modifier). Le commentaire reste facultatif et indépendant. **Les likes sont retirés du périmètre** et deviennent une évolution possible.

**Justification :**

- Une note (par exemple de 1 à 5) aide davantage à décider qu'un like, ce qui sert directement la proposition de valeur.
- Les favoris couvrent déjà le besoin de « garder » un spot. Likes, favoris et notes en même temps feraient trois mécanismes proches.
- Séparer la note du commentaire empêche de noter plusieurs fois le même spot en publiant plusieurs commentaires.

**Impact sur la modélisation :**

- **MCD :** association `NOTER` entre UTILISATEUR (0,n) et SPOT (0,n), porteuse des attributs `valeur` et `date_note`. Ce n'est pas une entité.
- **MLD :** table `note` dont la clé primaire est composée de `(utilisateur_id, spot_id)`, ce qui garantit l'unicité.
- **MPD :** contrainte `CHECK (valeur BETWEEN 1 AND 5)`.

**Priorité :** US-11 reste en P2.

---

## D3 — Compte obligatoire pour utiliser l'application

**Décision :** toutes les fonctionnalités, y compris la consultation de la carte et des fiches, nécessitent d'être connecté. Il n'y a pas d'acteur « visiteur » dans les cas d'utilisation.

**Conséquences :**

- La section 3.2.4 (Acteurs) est déjà cohérente avec ce choix.
- La précondition du parcours 3.4.1 (« ou accède aux fonctionnalités disponibles sans authentification ») doit être supprimée.
- Dans US-01, « En tant que visiteur » désigne simplement une personne pas encore inscrite : la formulation peut rester.
- Côté API, toutes les routes sauf l'inscription et la connexion sont protégées par l'authentification.
- Une session persistante est nécessaire pour ne pas imposer une connexion à chaque ouverture. C'est déjà ce que prévoit l'analyse d'éco-conception.

---

## D4 — Publication immédiate, modération a posteriori

**Décision :** un spot créé est publié immédiatement. La modération intervient ensuite : l'administrateur peut masquer un spot (US-17), puis, à terme, traiter les signalements (US-12 et US-15).

**Justification :** cohérent avec la découverte spontanée et le fonctionnement communautaire. Une validation préalable imposerait un administrateur disponible en permanence dès le MVP.

**Conséquence :** la notification « Spot validé » et la mention « validation des contenus » du README sont retirées.

---

## D5 — Statuts d'un spot

**Décision :** trois statuts au MVP.

| Statut | Signification | Qui le déclenche | Visible publiquement |
|---|---|---|---|
| `PUBLIE` | Statut par défaut à la création | Le système | Oui |
| `MASQUE` | Retiré de la vue publique par la modération | Administrateur | Non |
| `SUPPRIME` | Suppression logique : la ligne est conservée mais invisible | Créateur ou administrateur | Non |

**Transitions autorisées :**

- `PUBLIE` → `MASQUE` (administrateur)
- `MASQUE` → `PUBLIE` (administrateur)
- `PUBLIE` ou `MASQUE` → `SUPPRIME` (créateur ou administrateur)

**Justification :**

- « Signalé » n'est pas un statut du spot : c'est une information déduite de l'existence de signalements.
- « Brouillon » et « Archivé » ne répondent à aucune User Story du MVP. Ils deviennent des évolutions.
- La suppression logique conserve la cohérence des données liées (notes, commentaires, signalements) et garde une trace utile à la modération.

**Point à traiter avec le RGPD :** si un utilisateur demande la suppression de ses données, les spots supprimés logiquement devront être anonymisés ou purgés. Cette règle sera précisée dans la partie sécurité et données personnelles.

**Impact MPD :** type énuméré PostgreSQL (`enum` Prisma) `StatutSpot`, valeur par défaut `PUBLIE`.

---

## D6 — Catégories, tags et préférences

**Décision :**

- **Catégorie :** chaque spot a **une seule catégorie principale**, choisie dans une liste gérée par l'administrateur. La liste du README sera nettoyée pour supprimer les doublons de sens (« vue » et « sunset », « balade » et « randonnée »).
- **Tags :** un spot peut avoir plusieurs tags, choisis dans une **liste contrôlée**. Un tag précise le spot (gratuit, wifi, accessible à pied, coucher de soleil…) sans le classer.
- **Préférences utilisateur** (aventure, food, culture, nature, détente, coworking) : **hors MVP**. Elles seront stockées plus tard. La piste envisagée est une relation entre l'utilisateur et des catégories.

**Justification :** trois systèmes de classement qui se recoupent compliquent la saisie, les filtres et le modèle. Une catégorie sert à classer et à choisir le marqueur ; les tags servent à affiner.

---

## D7 — Photos

**Décision :** **au moins une photo obligatoire** à la création d'un spot, **cinq au maximum**.

**Justification :**

- Les photos authentiques sont un élément clé pour décider rapidement si un spot convient.
- Le plafond limite le volume stocké et transféré : c'est un argument d'éco-conception mesurable.

**Conséquences :**

- Le flux d'upload vers Cloudinary fait partie du MVP (US-07).
- La validation porte sur le type, le poids et le nombre de fichiers. Elle est faite côté serveur et doublée côté client.
- **MCD :** cardinalité SPOT (1,n) — PHOTO (1,1). Le minimum de 1 et le maximum de 5 sont des règles de gestion contrôlées par le backend : une base relationnelle ne les garantit pas seule.

---

## D8 — Gestion des comptes au MVP

**Décision :** le MVP comprend l'**inscription**, la **connexion** et la **déconnexion**.

La réinitialisation du mot de passe, la vérification de l'adresse e-mail, la photo de profil et la désactivation du compte deviennent des évolutions.

**Justification :** la vérification d'e-mail et la réinitialisation du mot de passe nécessitent un service d'envoi d'e-mails, donc une dépendance et une configuration supplémentaires. Elles n'apportent rien à la proposition de valeur principale.

**Conséquence :** la règle « L'adresse e-mail doit être vérifiée à l'inscription » du README passe en évolution. La règle « un seul compte par adresse e-mail » est conservée (contrainte d'unicité).

---

## D9 — Stockage des durées

**Décision :** la durée estimée d'un spot est stockée sous forme d'un **entier en minutes** (`duree_minutes`). Les paliers 30 min, 1 h, 2 h, demi-journée (240 min) et journée (480 min) sont des valeurs proposées dans l'interface, pas des libellés stockés.

**Justification :** la comparaison avec le temps disponible devient une simple condition (`duree_minutes <= temps_disponible`). Les paliers peuvent évoluer sans migration de la base.

**Impact MPD :** `CHECK (duree_minutes > 0)`.

*Proposition par défaut, à confirmer.*

---

## D10 — Cible d'un signalement

**Décision :** la table `signalement` possède deux clés étrangères facultatives, `spot_id` et `commentaire_id`. Exactement une des deux doit être renseignée.

**Garanties :**

- **Base de données :** une contrainte `CHECK` vérifie qu'une seule des deux colonnes est remplie. Prisma ne sait pas déclarer ce type de contrainte : elle sera ajoutée à la main dans la migration SQL.
- **Backend :** la même règle est vérifiée lors de la validation de la requête, pour renvoyer un message d'erreur clair.

**Priorité :** US-12 reste en P2. La décision est prise dès maintenant pour que le MCD soit complet.

*Proposition par défaut, à confirmer.*

---

## D11 — Pseudo unique

**Décision :** chaque utilisateur choisit un **pseudo**, unique, affiché comme auteur de ses spots et de ses commentaires.

**Justification :** il permet d'identifier l'auteur d'un contenu sans exposer son adresse e-mail. L'unicité évite les confusions entre deux auteurs.

*Proposition par défaut, à confirmer.*

---

## D12 — Statut des commentaires

**Décision :** un commentaire a les mêmes statuts qu'un spot : `PUBLIE`, `MASQUE` (par un administrateur) et `SUPPRIME` (suppression logique par son auteur ou un administrateur).

**Justification :** le traitement des signalements (US-15) prévoit de masquer un commentaire signalé, ce qui nécessite un statut. Utiliser les mêmes valeurs que pour les spots garde un modèle homogène.

*Proposition par défaut, à confirmer.*

---

## D13 — Traitement des signalements

**Décision :** un signalement a un statut `EN_ATTENTE`, `TRAITE` ou `CLASSE_SANS_SUITE`, et une date de traitement.

**Justification :** US-15 prévoit de masquer le contenu ou de classer le signalement sans suite. Enregistrer l'administrateur qui a traité le signalement n'est pas retenu, pour garder un modèle simple. Cela pourra être ajouté plus tard si un suivi plus précis est nécessaire.

*Proposition par défaut, à confirmer.*

---

## D14 — Adresse et conseil d'un spot

**Décision :** un spot peut avoir une **adresse** et un **conseil** pratique, tous deux facultatifs. Les horaires et les conditions d'accès restent des évolutions.

**Justification :** la maquette affiche l'adresse du spot et des conseils de la communauté. L'adresse est plus lisible que des coordonnées GPS. Un seul champ « conseil » couvre l'essentiel sans alourdir le formulaire.

---

## D15 — Informations du profil

**Décision :** le profil peut contenir un **prénom**, un **nom**, une **ville** et une **photo de profil**, tous facultatifs. Seuls le pseudo, l'e-mail et le mot de passe sont demandés à l'inscription. La date d'acceptation des conditions d'utilisation est enregistrée.

**Justification :** la maquette du profil affiche ces informations. Les rendre facultatives respecte le principe de minimisation des données du RGPD : l'utilisateur choisit ce qu'il partage.

---

## D16 — Liste des catégories

**Décision :** dix catégories sont retenues : Café, Coworking, Restauration, Bar et rooftop, Point de vue, Plage et baignade, Nature et randonnée, Culture et patrimoine, Marché, Activité.

**Justification :** cette liste couvre les besoins des personas (par exemple les cafés et coworkings pour les digital nomads) et supprime les doublons des premières listes (« vue » et « sunset », « balade » et « randonnée »).

---

## D17 — Charte graphique de référence

**Décision :** la charte de la maquette fait référence : police **Poppins**, couleurs Dark Teal `#0F4C5C`, Coral Glow `#FF7F50`, Muted Teal `#7A9E7E`, Carbon Black `#1E1E1E`, blanc et gris clair `#F5F5F5`. Les nuances intermédiaires sont des opacités de ces couleurs.

**Justification :** les premiers documents citaient Inter et d'autres noms de couleurs. La maquette, plus récente et plus aboutie, est retenue pour que le dossier, la maquette et le code utilisent la même charte.

---

## D18 — Bouton « Partager »

**Décision :** le bouton « Partager » reste visible sur la fiche d'un spot dans la maquette, mais le partage n'est pas dans le backlog du MVP. Il sera développé en évolution.

**Justification :** il fait partie de l'expérience envisagée et ne nécessite aucune donnée en base (partage du lien de la fiche). Il n'a donc aucun impact sur le MCD.

---

## Points techniques restant à décider

Ces choix ne changent pas le périmètre fonctionnel. Ils seront tranchés avec le cahier des charges technique.

| Sujet | Question |
|---|---|
| Tuiles cartographiques | Quel fournisseur de tuiles pour MapLibre ? Impact élevé selon l'analyse éco. |
| Géocodage | Quel service pour la recherche manuelle d'un lieu (repli si la géolocalisation est refusée) ? |
| Requêtes géographiques | Simple zone latitude/longitude avec index, ou PostGIS (moins bien pris en charge par Prisma) ? |
| Authentification | Session avec cookie `httpOnly` ou jeton JWT ? |
| Validation serveur | Quelle librairie de validation des entrées ? |
| Mesure éco | Quels outils et quelles mesures avant/après (EcoIndex, Lighthouse, onglet Réseau) ? |
| Règles floues du README | Critère de détection d'un spot en doublon ; seuil de masquage automatique après signalements. |

---

## Récapitulatif du backlog après décisions

| Priorité | User Stories |
|---|---|
| **P1 — MVP** | US-01 à US-09, US-16 (temps disponible), US-17 (masquer un spot), US-18 (gérer ses spots) |
| **P2** | US-10 commenter, US-11 noter, US-12 signaler, US-13 consulter son profil |
| **P3** | US-14 modifier son profil, US-15 traiter les signalements |
| **Évolutions** | Likes, préférences, brouillon/archivage, vérification e-mail, mot de passe oublié, suspension de compte, notifications, offre professionnelle |
