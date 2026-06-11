# Démarche d’éco-conception

Dans le cadre du développement de Spotly, plusieurs choix techniques et fonctionnels ont été envisagés afin de limiter l’impact environnemental de l’application tout en conservant une bonne expérience utilisateur.

## Optimisation des images

Les images représentent une part importante des données échangées par l’application. Afin de réduire leur poids, elles seront compressées automatiquement lors de leur envoi et converties dans un format optimisé comme WebP. Les métadonnées inutiles pourront également être supprimées.

## Chargement progressif des contenus

Les contenus visuels et les données seront chargés uniquement lorsqu’ils sont nécessaires. Cette approche permet d’éviter le téléchargement de ressources non consultées par l’utilisateur et d’améliorer les performances de l’application.

## Gestion optimisée de la carte

La carte interactive constitue l’élément principal de Spotly. Pour limiter la quantité de données chargées, seuls les spots présents dans la zone actuellement visible seront récupérés. Les marqueurs proches seront regroupés grâce à un système de clustering afin de conserver une interface fluide même lorsque le nombre de spots devient important.

## Réduction des appels réseau

L’application limitera le nombre de requêtes envoyées au serveur en regroupant certaines opérations et en évitant les rafraîchissements inutiles. Cette approche permet de réduire la consommation de bande passante et les ressources utilisées côté serveur.

## Interface légère

L’interface privilégiera la simplicité avec un nombre limité d’animations et d’effets graphiques. L’objectif est de proposer une navigation rapide tout en réduisant les ressources nécessaires à l’affichage des pages.

## Optimisation de la base de données

La base de données sera conçue de manière à faciliter les recherches géographiques et à limiter les traitements inutiles. Les données obsolètes ou non utilisées pourront être archivées afin de conserver de bonnes performances.

## Limitation des dépendances

Le projet utilisera uniquement les bibliothèques nécessaires à son fonctionnement. Cette démarche permet de réduire la taille de l’application et de limiter les ressources nécessaires à son exécution.

## Conclusion

L’éco-conception de Spotly repose sur des choix simples mais efficaces : optimisation des images, chargement dynamique des données, réduction des requêtes réseau et interface légère. Ces bonnes pratiques permettent d’améliorer les performances de l’application tout en limitant son impact environnemental.