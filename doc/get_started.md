 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# GET STARTED

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Introduction](#introduction)

![border](../assets/line/border_deco_rb.png)

# Mise en place

- Télécharger/ ou copier le driver Maven JDB sur le site [jdbc.postgresql.org](https://jdbc.postgresql.org/download/)

- Puis nous allons copier la dependance de Maven qui ressemble à ceci :

```
  <dependency>
      <groupId>org.postgresql</groupId>
      <artifactId>postgresql</artifactId>
      <version>42.7.4</version>
  </dependency>
```

- Et enfin nous allons ajouter la dependance dans notre fichier pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>testoto</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>23</maven.compiler.source>
        <maven.compiler.target>23</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <!-- Dépendance pour le pilote JDBC PostgreSQL -->
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <version>42.7.4</version>
        </dependency>
    </dependencies>

</project>
```

# Bases du code

![border](../assets/line/line-pink-point_r.png)

- Dans un premier temps au même niveau que Main
- Nous allons créer une nouvelle classe `DbFunctions` qui va contenir les éléments suivants :

```java
package org.example;

public class DbFunctions {
    public Connection connect_to_db();
}
```

- Cependant **Connection** pose un problème d'import
- Nous allons donc sur le dossier main qui porte le nom de notre application
- puis nosu allons faire le cibler avec un click droit et faire `Open modules settings`
- Puis nous allons dans la section `libraries` ou nous allons faire `+` afin de telecharger le driver que nous avons récupéré sur le site

- Ce qui nous permet d'importer la librairie ( premeir import)

```java
import java.sql.Connection;
```

- Voila a quoi devrait ressembler notre classe DbFunctions au debut

```java
package org.example;

import java.sql.Connection;

public class DbFunctions {
    public Connection connect_to_db(){
Connection conn=null;
}
}
```

![border](../assets/line/line-pink-point_r.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
