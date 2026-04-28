# Docker host

### Hôte Docker et le système d'exploitation

* Version stable de l'OS, avec le strict minimum pour héberger le Docker Engine
* Disposer d'un machine (hôte) dédiée à la seule tâche de Docker Engine
* Mise à jour régulière du système d'exploitation
* Suivre le principe d'"immutable infrastructure" que l'on peut résumé ainsi: "Une fois déployée, si on doit modifier, on reconstruit à neuf"

{% embed url="https://www.hashicorp.com/en/resources/what-is-mutable-vs-immutable-infrastructure" %}

{% embed url="https://docs.docker.com/engine/security/" %}

### Stockage

Postionner les données Docker (/var/lib/docker) sur un disque

* SSD
* dédié (et non au sein de l'OS)

### CGroup

Activer le cgroup2 (gestion des ressources par processus)

{% embed url="https://kubernetes.io/docs/concepts/architecture/cgroups/#using-cgroupv2" %}

### Logs

Afin de ne pas consommer inutilement de la RAM, il est important d'application une stratégie de gestion des logs. A minima:

* Mettre en place une rotation
* Limiter le niveau de verbosité

### Docker.sock

Ne jamais exposer le "daemon socket" via le réseau (même prinicpe que pour MySql).

{% embed url="https://docs.docker.com/engine/security/protect-access/#use-ssh-to-protect-the-docker-daemon-socket" %}

{% embed url="https://docs.docker.com/engine/security/" %}

### API

Si des API doivent être accessibles à travers le réseau, activer le TLS authentication.

{% embed url="https://docs.docker.com/engine/security/protect-access/#use-tls-https-to-protect-the-docker-daemon-socket" %}

### Utilisateur root

Favoriser l'utilisation d'un utilisateur à droits limités pour exécuter votre Docker Engine:

* Soit en favorisant la commande "sudo docker" plus que d'ajouter votre utilisateur dans le groupe Docker
* Soit en exécutant Docker en mode "rootless"

{% embed url="https://docs.docker.com/engine/security/rootless/" %}

{% embed url="https://docs.docker.com/engine/security/rootless/tips/" %}

{% embed url="https://docs.docker.com/engine/security/rootless/troubleshoot/" %}

### Mise en place d'outils d'audit

Réaliser des audits régulières pour anticiper des mauvaises utilisations de votre infrastructure.

{% embed url="https://docs.docker.com/guides/admin-user-management/audit-and-monitor/" %}

### Utilisation d'une stratégie de rôle

Dans une structure organisationnelle de production, allouer des rôles aux différents intervenants sur votre infrastructure Docker.

> Role-based access control (RBAC) is a method of regulating access to computer or network resources based on the roles of individual users within your organization.
>
> K8s web site

{% embed url="https://kubernetes.io/docs/reference/access-authn-authz/rbac/" %}

