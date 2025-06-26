# Dev Team Deploy

Votre équipe de développement aura pour objectifs de déployer une infrastructure de[ ce type](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html).

* Détecter et arrêter les instances qui tournent hors des heures de services (vacances, nuits, congés).
* Détecter des instances qui tournent et qui sont inexploitées et les arrêter.
* Détecter des adresses ip publiques inutilisées (mise à jour du DNS si besoin).
* Livrer les différents accès (aws console, access token, ssh key, windows password).
