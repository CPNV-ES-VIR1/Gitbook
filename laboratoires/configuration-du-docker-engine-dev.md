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
docker --version
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
//expected result
Docker version 29.4.1, build 055a478
```
{% endcode %}

{% embed url="https://docs.docker.com/engine/release-notes/29/" %}

## Limitations

Qu'identifiez-vous comme pratique à adapter pour un passage en production ?
