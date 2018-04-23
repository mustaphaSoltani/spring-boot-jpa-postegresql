# spring-boot-jpa-postegresql

Dans ce projet, j'ai créé un exemple de pool de connexions par Spring Boot , Spring Data JPA , PostegreSQL et HikariCP.  
Anisi, j'ai créé une interface et étendu les données Spring CrudRepository qui sont chargées par Hibernate automatiquement à partir du fichier import.sql.

---

## Les outils utilisés dans ce projet sont:

* *__Spring Boot 1.5.1.RELEASE__* :  permet de créer facilement des applications Spring

* *__Spring Data 1.13.0.RELEASE__* : vise à améliorer la mise en œuvre de la couche d'accès aux données.  
    Avec Spring-Data, écrire des méthodes de requête à la base se fait en 3+1 étapes:  
	    * Déclarer une interface Repository,  
	    * Ecrire la signature de la méthode de requête (CRUD ou de recherche),  
	    * Configurer Spring pour la génération automatique,  
	    * Appeler dans le client (ou test unitaire) les méthodes du Repository  

* *__Hibernate 5__* : est une solution open source de type ORM (Object Relational Mapping) qui permet de faciliter le développement de la couche persistance d'une application et la recherche de données dans une base de données. Hibernate permet donc de représenter une base de données en objets Java et vice versa.

* *__HikariCP 2.6__* : Il s'agit d'un framework de pooling de connexions JDBC très léger (Un pool de connexions est un cache de connexions de base de données maintenu de sorte que les connexions peuvent être réutilisées lorsque des demandes futures à la base de données sont requises)

* *__Maven__*: Maven est un outil de gestion et d'automatisation de production des projets logiciels Java en général et Java EE en particulier.
          Chaque projet ou sous-projet est configuré par un POM, se matérialise par un fichier pom.xml à la racine du projet, qui contient les informations nécessaires à Maven pour traiter le projet (nom du projet, numéro de version, dépendances vers d'autres projets, bibliothèques nécessaires à la compilation, noms des contributeurs, etc.)

* *__Java 8__*
-----------------
## Comment Configurer et Initialiser la base de données?
- Configuration la source de données Postegres dans application.propreties: 
```bash
          spring.database.driverClassName=org.postgresql.Driver
          spring.datasource.url=jdbc:postgresql://localhost:5432/projet1
          spring.datasource.username=postgres
          spring.datasource.password=admin
```

- Ajouter les paramètres HikariCP dans application.propreties:
```bash
           spring.datasource.hikari.connection-timeout=60000
           spring.datasource.hikari.maximum-pool-size=5
```
- Ajouter la dependance Postegres dans pom.xml; 
```bash
               <dependency>
                 <groupId>org.postgresql</groupId>
                 <artifactId>postgresql</artifactId>
                 <scope>runtime</scope>
              </dependency>
  ```
  Pour voir l'arbre de dépendances du projet on utilse la commande:
  ```bash
  mvn dependency:tree
  ```
        
