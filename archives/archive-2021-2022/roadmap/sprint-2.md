# Sprint 2

### Objectifs <a href="#objectif" id="objectif"></a>

Ce sprint aura pour objectif de mettre en oeuvre l'architecture présentées ici:

{% file src="../../../.gitbook/assets/ClassDiagramOverview.puml" %}

Tout en réalisant les fonctionnalités suivantes:

![](<../../../.gitbook/assets/ClassDiagramOverview (1).png>)

### Dev Team Core

* Réunir le code commun produit par les différentes dev team.
* Configuration du dépôt.
* Annoncer le dépôt comme étant éligible pour npm package.
* Intégrer le package npm dans la dev team deliver.

### Dev Team Deploy

* Gestion des subnets.
* Gestion des routes.

### Dev Team Backup and Archive

* Gérer la rotation des snapshots et amis.

### Dev Team Cost Limitation

* Suppression des budgets.
* Gestion des alertes.
* Gestion des rapports.

### Dev Team Deliver

* Génératon du json de "sortie" contenant:
  * la région
    * le vpc
      * les sous-réseaux
      * les routes
        * les instances.
        * les groupes de sécurités.
* Extraire et présenter les données pour accéder aux instances:
  * clés ssh pour les instances Linux.
  * mot de passes pour les instances Windows.

{% file src="../../../.gitbook/assets/VIR1-Json-Master.json" %}

