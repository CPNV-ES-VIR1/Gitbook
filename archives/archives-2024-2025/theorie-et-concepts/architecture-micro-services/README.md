# Architecture micro-services

Introduction



L’architecture **microservices** est un style d’organisation des applications qui consiste à décomposer un système en un ensemble de services indépendants, <mark style="color:orange;">chacun responsable d’une fonctionnalité métier spécifique</mark>. Cette approche contraste avec les architectures monolithiques, où toutes les fonctionnalités sont regroupées dans une seule application.

<mark style="color:orange;">Chaque microservice est généralement</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**stateless**</mark>, c’est-à-dire qu’il ne conserve pas d’état entre deux requêtes. Cela facilite <mark style="color:orange;">sa gestion, son redémarrage, sa réplication et sa montée en charge</mark>. En effet, cette propriété est essentielle pour permettre **l’autoscaling**, une technique où les instances de services sont automatiquement multipliées ou réduites en fonction de la charge, assurant ainsi performance et résilience.

Pour centraliser les accès aux différents services, <mark style="color:orange;">un</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**API Gateway**</mark> est souvent utilisé. Ce composant <mark style="color:orange;">agit comme un point d’entrée unique pour les clients.</mark>&#x20;

En plus de la gestion du routage, il est responsable de:

* l’authentification,&#x20;
* la limitation de débit,&#x20;
* et parfois la transformation des requêtes.

<mark style="color:orange;">Le déploiement et la gestion de ces services sont généralement automatisés par un</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**orchestrator**</mark> comme Kubernetes.&#x20;

L’orchestrateur gère:

* <mark style="color:orange;">le cycle de vie des services</mark> (déploiement, mise à l’échelle, tolérance aux pannes),&#x20;
* leur découverte,&#x20;
* et leur communication.

Enfin, pour garantir des livraisons fréquentes, fiables et automatisées, <mark style="color:orange;">les microservices s’intègrent naturellement dans une</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**pipeline CI/CD/CD**</mark> (Intégration Continue / Distribution Continu / Déploiement Continu). Cela permet de tester, construire et déployer chaque service indépendamment, réduisant les risques et accélérant le cycle de développement.

