# Les conteneurs

### Limitation des ressources disponibles

Limiter les ressources allouées aux conteneurs

{% embed url="https://docs.docker.com/engine/containers/resource_constraints/" %}

### MULTISTAGE

Utiliser le multi-stage afin de réduire la taille des images

{% embed url="https://docs.docker.com/build/building/multi-stage/" %}

### Lecture seule

Limiter les droits en écriture des conteneurs si possible.

{% embed url="https://docs.linuxserver.io/misc/read-only/" %}

### Gestion des données sensibles

* Ne jamais stocker des données sensibles dans vos images (clé d'api, nom d'utilisateur pour une db)
* Favoriser l'utilisation de Docker Secrets ou des solutions externes (AWS Secret Manager, GithubSecrets)

{% embed url="https://docs.docker.com/engine/swarm/secrets/" %}

* Limiter l'utilisation de variables d'environnements pour les données sensibles. Utiliser les secrets files à la place

{% embed url="https://docs.docker.com/engine/swarm/secrets/#how-docker-manages-secrets" %}
