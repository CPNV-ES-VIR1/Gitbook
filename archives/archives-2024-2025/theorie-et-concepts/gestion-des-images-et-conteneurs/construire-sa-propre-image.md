# Construire sa propre image

{% embed url="https://docs.docker.com/build/building/best-practices/" %}

## Introduction à la création d’image Docker

Docker permet de **construire des environnements d'exécution isolés** et portables, appelés _conteneurs_, à partir d’images. Ces images sont créées à partir d’un fichier de configuration appelé **Dockerfile**.

## Image de base

Toute image Docker commence par une **image de base**, qui sert de fondation. Il peut s'agir, par exemple, d'une distribution Linux minimale (`alpine`, `ubuntu`) ou d’une image applicative comme `node`, `python`, ou `nginx`. Elle fournit l’environnement initial dans lequel les autres couches seront ajoutées.

{% embed url="https://docs.docker.com/build/building/base-images/" %}

## Dockerfile et layers

Le **Dockerfile** décrit, étape par étape, comment construire l’image finale. Chaque instruction (`FROM`, `RUN`, `COPY`, `CMD`, etc.) correspond à une **couche** (_layer_), ce qui permet une **mise en cache** efficace : seules les couches modifiées doivent être reconstruites lors des changements.

Exemple simple :

```docker
FROM python:3.11-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "main.py"]
```

{% embed url="https://docs.docker.com/get-started/docker-concepts/building-images/understanding-image-layers/" %}

## Utilisation de volumes

Un volume permet de **partager des données** entre l’hôte et le conteneur, ou entre plusieurs conteneurs. Il existe deux types :

* **Volume Docker natif** : géré par Docker (`docker volume create`)
* **Bind mount** : lie un dossier local à un chemin dans le conteneur (`-v $(pwd):/app`)

Cela facilite le **développement local** sans reconstruire l’image à chaque modification.

{% embed url="https://docs.docker.com/engine/storage/volumes/" %}

{% hint style="warning" %}
Réaliser le laboratoire "[Déployement Nginx](../../labos/deploiement-nginx/)" pour pratiquer toutes les notions abordées ci-dessus.
{% endhint %}

## Réseaux Docker

Les conteneurs peuvent être connectés à un **réseau Docker personnalisé**, permettant une **communication sécurisée et interne** entre eux, sans exposer les ports au système hôte. Par défaut, Docker crée un pont (`bridge`), mais il est courant d’en créer un nommé :

```bash
docker network create my-network
```

{% embed url="https://docs.docker.com/engine/network/" %}

## Docker Compose

**Docker Compose** permet de **décrire et d’orchestrer plusieurs services** (conteneurs) dans un seul fichier `docker-compose.yml`. Il simplifie :

* la configuration des services
* le montage des volumes
* la définition des réseaux
* le démarrage/arrêt en un seul appel (`docker compose up`)

C’est particulièrement utile pour des environnements multi-conteneurs (base de données + API + frontend, par exemple).

{% hint style="warning" %}
Réaliser le laboratoire "Déployement WordPress" pour pratiquer toutes les notions abordées ci-dessus.
{% endhint %}
