# Choix de l'architecture

Source: [AWS - the difference between monolithic and microservices architecture](https://aws.amazon.com/compare/the-difference-between-monolithic-and-microservices-architecture/)

### Quand utiliser une architecture monolithique versus architecture de microservices <a href="#seo-faq-pairs-when-to-use-mono-vs-micro" id="seo-faq-pairs-when-to-use-mono-vs-micro"></a>

L'architecture monolithique et l'architecture de microservices aident les développeurs à créer des applications selon différentes approches. Il est important de comprendre que les microservices ne réduisent pas la complexité d'une application. Au contraire, la structure des microservices révèle les complexités sous-jacentes et permet aux développeurs de créer, de gérer et de mettre à l'échelle de grandes applications de manière plus efficace.

Lorsque le choix entre le développement d'une architecture microservices ou monolithique s'impose, vous pouvez prendre en compte les facteurs suivants.

#### **Taille de l'application**

<mark style="color:orange;">L'approche monolithique est plus adaptée à la conception d'une application ou d'un prototype simple</mark>. Comme les applications monolithiques utilisent une base de code et un cadre uniques, les développeurs peuvent créer le logiciel sans intégrer plusieurs services. Les applications de microservices peuvent nécessiter beaucoup de temps et d'efforts de conception, ce qui ne justifie pas le coût et les avantages de très petits projets.&#x20;

Dans le même temps, l'architecture des microservices est plus adaptée à la création d'un système complexe. Elle fournit une base de programmation solide à votre équipe et soutient sa capacité à ajouter plus de fonctionnalités de manière flexible. Par exemple, Netflix utilise AWS Lambda pour faire évoluer son infrastructure de streaming et gagner du temps de développement.

#### **Compétences de l'équipe**

Malgré leur flexibilité, <mark style="color:orange;">le développement à l'aide de microservices nécessite un ensemble de connaissances et une réflexion conceptuelle différents</mark>. Contrairement aux applications monolithiques, le développement de microservices <mark style="color:orange;">nécessite une compréhension de l'architecture cloud, des API, de la conteneurisation et d'autres compétences spécifiques aux applications cloud modernes.</mark> En outre, le dépannage des microservices peut s'avérer difficile pour les développeurs qui découvrent l'architecture distribuée.

#### **Infrastructure**

Une application monolithique s'exécute sur un seul serveur, tandis que les applications de microservices bénéficient davantage de l'environnement cloud. Bien qu'il soit possible d'exécuter des microservices à partir d'un seul serveur, <mark style="color:orange;">les développeurs hébergent généralement des microservices auprès de fournisseurs de services cloud afin de garantir la capacité de mise à l'échelle, la tolérance aux pannes et la haute disponibilité.</mark>

Avant de pouvoir commencer à utiliser des microservices, il est nécessaire de mettre en place l'infrastructure adéquate. <mark style="color:orange;">La mise en place des outils et du flux de travail pour les microservices vous demande plus d'efforts, mais ces derniers sont à privilégier pour la création d'une application complexe et évolutive.</mark>

