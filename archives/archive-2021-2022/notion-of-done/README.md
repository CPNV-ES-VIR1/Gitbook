# Notion of done

### Conception

* Le diagramme de classes est cohérent avec le code livré.
* Les diagrammes de séquences sont cohérents avec le code livré.

### Paramètres d'entrée

* Les paramètres d'entrées proviennent d'un JSON.
* La structure du JSON définie (en équipe) doit être respectée.
* Les ressources sont adressées par leur nom (tag name value).

### SDK

* Le SDK livré par AWS:
  * Est exploité au maximum (aucun usage de type API sans SDK).
  * Utilisation des objets et méthods livrées.
  * Gestion des exceptions.

### Tests

* Les tests respectent la [structure décrite ici](test-sample.md).
* Toutes les fonctionnalités sont testées (selon les critères du backlog).
* Encapsulation des tests (pas de dépendance entre les tests).
* Les séquences sont testés automatiquement (test niveau d'intégration).

### Dépôt

* Le Readme permet de rapidement pouvoir collaborer
  * [Exemple de readme](https://www.makeareadme.com/)
    * Comment configurer l'environnement de dév.
    * Comment exécuter les tests.
    * Comment déployer le code.
* Le wiki mentionne les choix technologiques
* La stratégie de branches
  * La branche <mark style="color:orange;">master/main</mark> sera mise à jour en fin de module, avant la semaine com (release).
  * La branche <mark style="color:orange;">develop:</mark>
    * intégrera les nouvelles fonctionnalités.
    * sera la branche de démonstration lors des reviews.
  * Une branch <mark style="color:orange;">release</mark> sera utilisée pour la défense finale, lors de la semaine com.
* Centralisation de tous les bugs (issues).

### Documentation

*   Les méthodes/fonctions doivent présentées un entête selon ce modèle:



```
    /**
     * @brief This method returns the number of CartItems present in the Cart
     * @param distinct : boolean a distinct constraint
     * @returns {number} : number of CartItems
     * @exception EmptyCartException is thrown if the Cart is empty
     * @link https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/EC2.html#allocateAddress-property
     */
```

### Gestion des credentials

La méthode de gestion des crédentials doit être identiques dans toutes les dev teams.

### Log

Toutes les actions entreprises par vos application sur le cloud devront être logées.
