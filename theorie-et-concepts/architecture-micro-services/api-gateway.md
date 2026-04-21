# API Gateway

Source: [Redhat - What does an API gateway do ?](https://www.redhat.com/en/topics/api/what-does-an-api-gateway-do)

Présentation

Une passerelle d'API est un outil de [gestion des API](https://www.redhat.com/fr/topics/integration/la-gestion-des-api-quest-ce-que-cest) qui se positionne entre un client et un ensemble de services back-end. Dans ce contexte, le client est une application exécutée sur l'appareil d'un utilisateur et les services back-end sont ceux qui s'exécutent sur les serveurs d'une entreprise. Une [API (Application Programming Interface, ou interface de programmation d'application)](https://www.redhat.com/fr/topics/api/what-are-application-programming-interfaces) est un ensemble de définitions et de protocoles qui facilite la création et l'intégration des applications.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption><p><a href="https://microservices.io/patterns/apigateway.html">Microservices.io</a></p></figcaption></figure>

La passerelle d'API est un composant du processus de distribution d'applications, c'est-à-dire l'ensemble des services qui font fonctionner une application. Elle agit comme un proxy inversé (reverse proxy) qui accepte tous les appels d'[API](https://www.redhat.com/fr/topics/api/what-are-application-programming-interfaces), rassemble les différents services requis pour y répondre et renvoie le résultat approprié. <mark style="color:orange;">Plus simplement, une passerelle d'API est un composant logiciel qui intercepte les appels d'API émis par un utilisateur et les achemine vers le service back-end approprié.</mark>

### Utilité des passerelles d'API <a href="#utilite-des-passerelles-dapi" id="utilite-des-passerelles-dapi"></a>

La plupart des API d'entreprise sont déployées à l'aide de passerelles d'API. Celles-ci gèrent souvent des tâches courantes utilisées dans un système de services d'API, comme l'authentification des utilisateurs, la limitation du débit et le calcul de statistiques.

En résumé, un service d'API accepte une demande distante et renvoie une réponse. Dans la pratique, ce n'est pas aussi simple. En effet, <mark style="color:orange;">l'hébergement d'API à grande échelle présente certains risques</mark>.

* Pour protéger les API d'une utilisation abusive et excessive, il faut mettre en œuvre un service d'authentification et des limites de débit.&#x20;
* Pour comprendre comment les utilisateurs exploitent les API, il faut ajouter des outils d'analyse et de surveillance.
* Il faut connecter les [API monétisées](https://www.redhat.com/fr/topics/integration/la-monetisation-des-api-quest-ce-que-cest) à un système de facturation.
* Dans une architecture de [microservices](https://www.redhat.com/fr/topics/microservices/what-are-microservices), une simple demande peut entraîner des appels à des dizaines d'applications distinctes.
* Au fil du temps, il faudra supprimer certains services d'API et en ajouter d'autres, tout en s'assurant que les clients pourront toujours trouver tous ces services au même endroit.

<mark style="color:orange;">L'objectif est de fournir aux clients une expérience simple et fiable, qui occulte la complexité sous-jacente</mark>. L'utilisation d'une passerelle d'API permet de dissocier l'interface client de la mise en œuvre back-end. Lorsqu'un client envoie une demande, la passerelle d'API la segmente en plusieurs demandes qu'elle achemine vers les services appropriés, produit une réponse et conserve une trace de toutes ces opérations.

### Rôle des passerelles d'API dans la gestion des API <a href="#role-dans-la-gestion-des-api" id="role-dans-la-gestion-des-api"></a>

La passerelle d'API est un des éléments du système de gestion d'API. Elle intercepte toutes les demandes entrantes et les transmet au système de gestion d'API, qui se charge de nombreuses fonctions essentielles.

Selon la mise en œuvre, les opérations que les passerelles d'API peuvent effectuer vont varier. Leurs principales fonctions incluent

* l'authentification,&#x20;
* le routage,&#x20;
* la limitation du débit,&#x20;
* la facturation,&#x20;
* la surveillance,&#x20;
* l'analyse,&#x20;
* l'application de politiques,&#x20;
* l'envoi d'alertes et,
* la sécurisation

Les passerelles d'API offrent les avantages suivants:

#### Faible latence (Low latency)

Pour garantir un niveau optimal de performances et d'utilisation des ressources, les passerelles d'API optimisent le routage du trafic et l'équilibrage de charge dans les services back-end en distribuant les demandes entrantes et en déléguant les tâches courantes telles que la terminaison SSL et la mise en cache. Les passerelles d'API réduisent ainsi la charge du serveur et l'utilisation de la bande passante, avec à la clé une diminution des besoins en capacités de serveur et en bande passante réseau et une amélioration de l'expérience utilisateur.

#### Gestion du trafic (Traffic management)

Pour garantir un niveau optimal de performances et d'utilisation des ressources, les passerelles d'API limitent et gèrent le trafic à l'aide de différents mécanismes conçus pour contrôler le débit et le volume des demandes entrantes.

* Les politiques de **limitation du débit (**[**rate limite**](https://datadome.co/bot-management-protection/what-is-api-rate-limiting/)**)** définissent le nombre maximal de demandes autorisées au cours d'une période donnée (par exemple, le nombre de demandes par seconde, minute ou heure) pour chaque client ou clé d'API afin d'éviter la surcharge des services back-end.
* Les politiques de **limitation des demandes (**[**request throttling**](https://www.tibco.com/glossary/what-is-api-throttling)**)** définissent des règles et des limites qui régulent le trafic des demandes, telles que les taux maximaux de demandes, les allocations en cas d'activité intense et les quotas.
* Les politiques de **contrôle de simultanéité (**[**concurrency control policies**](https://questdb.com/glossary/concurrency-control/)**)** définissent le nombre maximal de connexions ou de demandes simultanées qui peuvent être traitées en même temps par les serveurs back-end.
* Les politiques de type [**« coupe-circuit »**](https://docs.dapr.io/operations/resiliency/policies/circuit-breakers/) surveillent l'état et le temps de réponse des serveurs back-end. Elles bloquent ou redirigent aussi temporairement le trafic provenant de services ralentis ou en échec pour éviter les défaillances en cascade et assurer la stabilité globale du système.
* L'**équilibrage de charge dynamique (**[**dynamic load balancing**](https://aws.amazon.com/what-is/load-balancing/)**)** à partir de passerelles d'API permet de surveiller en continu l'état du serveur et d'ajuster le routage du trafic en temps réel pour traiter les pics de demande, écourter les temps de réponse et optimiser le débit.
