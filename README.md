# ZZ Book

Application microservice pour le cours de Technologie des conteneurs.

# Auteurs

Yassine BENGANA
Julien POLYCARPE

# Emplacement des divers élements

## Manifests Kubernetes

Présents dans le dossier kubernetes

## Docker-compose

Présent à l'emplacement src/docker-compose.yml

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

Présents dans le dossier compte-rendu