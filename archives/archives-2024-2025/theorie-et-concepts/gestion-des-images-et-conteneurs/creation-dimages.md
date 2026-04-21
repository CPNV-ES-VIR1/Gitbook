# Création d'images

## Introduction

Docker est un outil de conteneurisation qui permet aux développeurs de <mark style="color:orange;">créer, tester et déployer</mark> des applications rapidement. Un des éléments centraux de Docker est <mark style="color:orange;">l'image, qui représente un modèle immuable contenant tout ce qui est nécessaire pour exécuter une application</mark> :&#x20;

* le code,&#x20;
* les bibliothèques,&#x20;
* les variables d'environnement, et&#x20;
* les configurations par défaut.

## **Création et Gestion d'Images Docker**

### **Dockerfile**

Un Dockerfile est un script texte qui contient une série d'instructions pour assembler une image Docker. Chaque ligne du Dockerfile représente une commande qui sera exécutée pour créer l'image. Par exemple, l'instruction `FROM` spécifie l'image de base, tandis que `RUN` permet d'exécuter une commande dans le conteneur.

{% code fullWidth="false" %}
```docker
# syntax=docker/dockerfile:1
FROM node:18-alpine             //image de base
WORKDIR /app                    //chemin de travail appliqué aux prochaines commmandes
COPY . .                        //copie du local vers l'image ( "." = emplacement actuel)
RUN yarn install --production   //installation des dépendances avec yarn
CMD ["node", "src/index.js"]    //on utilise l'exécutable node pour lire le fichier index.js
EXPOSE 3000                     //mentionner que l'image va exposer le 3000
```
{% endcode %}

### **Build d'une image**

La commande `docker build` permet de <mark style="color:orange;">créer une image à partir d'un Dockerfile</mark>. Il est essentiel de suivre les bonnes pratiques lors de la rédaction du Dockerfile pour optimiser la taille de l'image et la vitesse de construction.

```docker
docker build -t getting-started .
```

{% embed url="https://docs.docker.com/build/building/best-practices/" %}

**Optimisation de la taille des images**

Pour réduire la taille des images Docker, utilisez des images de base légères comme `alpine`, nettoyez les caches des gestionnaires de paquets (`apt-get clean`), et <mark style="color:orange;">combinez les instructions du Dockerfile pour minimiser le nombre de couches</mark>.

```bash
apt update && apt install -y nodejs
```

**Tagging des images**

Lors de la construction d'une image, il est recommandé d'utiliser des tags explicites pour identifier les versions (par exemple, `myapp:1.0.0`). <mark style="color:orange;">Les tags permettent de gérer facilement les différentes versions d'une image</mark>.

{% embed url="https://docs.docker.com/reference/cli/docker/image/tag/" %}

#### **Sécurité des images**

Utilisez des images de sources fiables et <mark style="color:orange;">vérifiez régulièrement les vulnérabilités</mark>. Docker propose des outils comme `docker scan` pour analyser les images en local et identifier les vulnérabilités de sécurité.

{% embed url="https://docs.docker.com/docker-hub/repos/manage/vulnerability-scanning/" %}

#### **Nettoyage régulier**

Utilisez les commandes `docker system prune` et `docker image prune` pour nettoyer les images inutilisées et <mark style="color:orange;">éviter l'encombrement du disque dur local</mark>.

{% embed url="https://docs.docker.com/reference/cli/docker/image/prune/" %}

#### **Cohérence entre les environnements**

Assurez-vous que les images utilisées en développement sont les mêmes que celles déployées en production. Cela <mark style="color:orange;">garantit que l'application se comportera de la même manière dans les deux environnements</mark>.
