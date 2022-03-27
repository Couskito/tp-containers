# ZZ Book

Application microservice pour le cours de Technologie des conteneurs.

# Auteurs

Yassine BENGANA
Julien POLYCARPE

# Emplacement des divers élements

## Docker-compose

Présents à l'emplacement docker-compose/ :
- docker-compose/fil-rouge/docker-compose.yaml : docker-compose du fil rouge du TP
- docker-compose/wordpress/docker-compose.yaml : docker-compose de l'exemple wordpress du TP

## Ingress Kubernetes

Présents dans le dossier ingress_test. Contient un script bash initialisant un registre kind avec l'utilisation d'ingress, et également un service Ingress utilisé pour exposer le service productpage à l'extérieur du cluster. Non fonctionnel : le port forwarding ne semble pas être effectué.

## Scripts Kind

Présents dans le dossier kind_init :
- kind_registry.sh : script permettant la mise en place d'un cluster kind avec un registre local, à utiliser pour lancer les manifests kubernetes

Remarque : pour utiliser les images Docker locales via Kubernetes par la suite, effectuer les commandes suivantes dans le dossier docker-compose/fil-rouge/ pour les push dans le registre local initialisé avec Kind :
- docker compose build
- docker compose push

## Manifests Kubernetes

Présents dans le dossier kubernetes. Contient deux dossiers : celui pour le fil-rouge, et celui pour l'utilisation de kuard.

## Dockerfiles

Présents dans chaque dossier contenant le code d'un microservice :
- details : src/details/Dockerfile
- mongodb : src/mongodb/Dockerfile
- mysql : src/mysql/Dockerfile
- productpage : src/productpage/Dockerfile
- ratings : src/ratings/Dockerfile
- reviews : ne pas tenir compte du Dockerfile dans src/reviews/reviews-wlpcfg. Le code était non fonctionnel et l'image utilisée a finalement été docker.io/istio/examples-bookinfo-reviews-v1:1.16.2 

## Code des services

Le code des différents services est présent dans `src/`.

* `details` : Service de détails des livres, en ruby.
* `productpage` : Service point d'entrée des autres microservices, en python.
* `reviews` : Service contenant les commentaires sur les livres, appel `ratings`, en java.
* `ratings` : Service de gestion des notes des livres, en node.js.

## Définitions de l'API

L'API visible de l'utilisateur est définie dans le fichier `swagger.yaml`. Pour visualiser le fichier, vous pouvez utiliser le [Swagger editor](https://editor.swagger.io/).

## Compte rendu des TPs

Présents dans le dossier comptes-rendus.