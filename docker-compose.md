# Docker Compose

## Introduction

Docker Compose est un outil qui permet de définir et d’orchestrer plusieurs conteneurs Docker à partir d’un unique fichier de configuration YAML.

\
Là où Docker permet de lancer des conteneurs individuellement avec des commandes comme `docker run`, <mark style="background-color:$success;">Docker Compose simplifie la gestion d’applications composées</mark> de plusieurs services : API, base de données, cache, broker de messages, etc.

Avec un fichier `docker-compose.yml`, il devient possible de décrire l’ensemble de l’infrastructure applicative :&#x20;

* images utilisées,&#x20;
* ports exposés,&#x20;
* volumes,&#x20;
* variables d’environnement,&#x20;
* dépendances entre services et réseaux.&#x20;

Une simple commande comme `docker compose up` permet ensuite de démarrer tout l’environnement.

Docker Compose est particulièrement utile en développement local, pour reproduire facilement une architecture complète, partager un environnement standardisé entre développeurs et automatiser le lancement des services nécessaires à une application.

### En production

On utilise généralement un orchestrateur de conteneurs comme :

* Kubernetes\
  La solution la plus répandue aujourd’hui. Elle permet :
  * le déploiement distribué sur plusieurs serveurs,
  * l’auto-scaling,
  * la haute disponibilité,
  * le redémarrage automatique des conteneurs,
  * le rolling update,
  * la gestion avancée du réseau et du stockage.
* Docker Swarm\
  Plus simple que Kubernetes et intégré à Docker, mais aujourd’hui beaucoup moins utilisé dans les grandes infrastructures.
* Nomad\
  Une alternative légère et flexible proposée par [HashiCorp](https://www.hashicorp.com/?utm_source=chatgpt.com)

### OCI

L’écosystème des conteneurs repose aujourd’hui largement sur la norme OCI (_Open Container Initiative_).&#x20;

Cette initiative définit des standards ouverts pour les formats d’images et l’exécution des conteneurs, garantissant la compatibilité entre différents outils et plateformes.&#x20;

Grâce à OCI, une image construite avec Docker peut également être exécutée avec d’autres runtimes compatibles comme containerd ou Podman.&#x20;

Docker Compose s’inscrit donc dans un environnement plus large et standardisé, où les technologies de conteneurisation interopèrent autour de spécifications communes.

