* Ceci est un projet Maven. Assurez-vous que Maven est installé sur votre système.
* Il est recommandé d'utiliser un système d'exploitation basé sur Linux.
* Il se peut que vous ayez installé le logiciel XAMPP/LAMPP (par Bitnami) sur votre système. Au lieu d'utiliser la base de données fournie par XAMPP/LAMPP par Bitnami, il est recommandé d'installer ``mariadb-server`` et de l'utiliser comme base de données pendant l'exécution de cette application.  

###Comment fonctionner en local
1. Renommez ``src/main/resources/application.properties.example`` en ``src/main/resources/application.properties``.
1. Changez les propriétés de l'application (par exemple le nom d'utilisateur/mot de passe de la base de données) présentes dans ``resources/application.properties`` en fonction de votre serveur mysql local.
1. Allez dans application.properties et commentez / décommentez l'url front-end correspondante et entrez les clés API STRIPE
1. Créez une base de données appelée `ecommerce` avec `CHARACTER SET utf8mb4`` et `COLLATE utf8mb4_0900_ai_ci`. MariaDB ne supporte pas `COLLATE utf8mb4_0900_ai_ci`. Donc, si vous utilisez MariaDB, ouvrez le fichier `database-dump.sql` et remplacez `COLLATE utf8mb4_0900_ai_ci` par `COLLATE utf8mb4_general_ci`.  
1. Importez le fichier `database-dump.sql` dans celui-ci.
1. Pour exécuter l'application, lancez la commande ``sh run.sh`` c'est-à-dire exécutez le fichier ``run.sh``. 
1. Après avoir lancé l'application, allez sur http://localhost:8080/api/swagger-ui.html/
   
## Catégorie/Update/{id}
* L'entrée pour mettre à jour la catégorie via l'API est la suivante
```
{
    "categoryName" : "name",
    "imageUrl" : "url",
    "description" : "desc"
}
```


### En cas d'erreur "java.lang.IllegalStateException : Unable to load cache item error" :
- Allez dans pom.xml et commentez la portée de la dépendance "spring-boot-starter-tomcat".


## How to use prod profile
mvn package
java -jar -Dspring.profiles.active=prod <package name in target>

## Run in production server with latest changes in master


#admin access
email: admin@gmail.com
password: admin
firstname: admin

