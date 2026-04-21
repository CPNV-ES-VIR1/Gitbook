# Configuration du Docker Engine (dev)

## Intention

{% embed url="https://docs.docker.com/engine/" %}

Ce laboratoire a pour but de vous permettre de mettre en place un environnement de développement basé sur Docker. Il est important de suivre rigoureusement la documentation officielle afin de réaliser une installation correcte et fonctionnelle du moteur Docker. \
\
Une attention particulière est portée à la compréhension des différentes étapes de configuration et des choix effectués.

À l’issue du laboratoire, vous serez amenés à analyser de manière critique votre installation, en identifiant ses limitations, ainsi que les éléments essentiels à anticiper lors d’un déploiement en environnement de production. Environnement de production que vous devrez mettre en place dans la partie projet de l'unité.



## Prérequis

Il est important d'avoir lu l'introduction Docker publiée ici:

{% content-ref url="../theorie-et-concepts/docker/" %}
[docker](../theorie-et-concepts/docker/)
{% endcontent-ref %}

Identifiez bien les différents composants de l'écosystème Docker (architecture) afin de pouvoir ensuite les manipuler correctement sur votre environnement.



## Installation

Voici la documentation en fonction de votre système d'exploitation

* Linux

{% embed url="https://docs.docker.com/engine/install" %}

* Windows

{% embed url="https://docs.docker.com/desktop/setup/install/windows-install/" %}

* Mac OS

{% embed url="https://docs.docker.com/desktop/setup/install/mac-install/" %}

## Résultat à obtenir

* Lister les conteneurs présents, peu importe leur état

{% code overflow="wrap" expandable="true" %}
```
docker ps -a
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
//expected result
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```
{% endcode %}

* Récupérer l'image de NGINX

{% code overflow="wrap" expandable="true" %}
```
docker pull nginx:latest
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
//expected result
latest: Pulling from library/nginx
448ea5cac5d5: Pull complete 
88d1d984b765: Pull complete 
84e114c2bb36: Pull complete 
5435b2dcdf5c: Pull complete 
054715a6bffa: Pull complete 
4a038fd18db1: Pull complete 
7b5d674621c2: Pull complete 
cc0cf959117b: Download complete 
3eff0a97d435: Download complete 
Digest: sha256:7f0adca1fc6c29c8dc49a2e90037a10ba20dc266baaed0988e9fb4d0d8b85ba0
Status: Downloaded newer image for nginx:latest
docker.io/library/nginx:latest

```
{% endcode %}

* Constuire le conteneur

{% code overflow="wrap" expandable="true" %}
```
docker container create nginx:latest -t my-fist-container
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
```
{% endcode %}
