 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# Collections et Gestion des Exceptions

![border](../assets/line/line-pink-point_l.png)

## Missions

- [ ] [Découvrir les Collections Java]()

  - [ ] [List (ArrayList, LinkedList)](#les-collections-list-arraylist-linkedlist)
  - [ ] [Set (HashSet, TreeSet)](#set-hashset-treeset)
  - [ ] Map (HashMap, TreeMap)
  - [ ] Utilisation des Generics

- [ ] Gérer les exceptions

  - [ ] Utilisation de try-catch-finally
  - [ ] Propagation des exceptions avec throws
  - [ ] Création d'exceptions personnalisées

- [ ] Exercices pratiques
  - [ ] Manipuler une liste d'objets (ajouter, supprimer, trier)
  - [ ] Écrire un programme qui gère les exceptions lors de la lecture d'un fichier

![border](../assets/line/border_deco_rb.png)

# Découvrir les Collections Java

## Point de départ Hello World

- Pour commencer nous allons partir d'un projet vierge

```java
package org.example;
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## Les Collections List (ArrayList, LinkedList)

### Définition :

- Une **List** est une collection ordonnée qui permet des éléments dupliqués.
- **ArrayList** est rapide pour les accès,
- **LinkedList** est plus efficace pour les modifications.

### Benchmark ARRAYLIST LINKEDLIST:

| Type de Tableau/Collection | Structure de Données     | Consommation Mémoire | Cas d'utilisation                             |
| -------------------------- | ------------------------ | -------------------- | --------------------------------------------- |
| Array (Tableau simple)     | Tableau statique         | Faible               | Manipulations simples avec taille fixe        |
| ArrayList                  | Tableau dynamique        | Modérée              | Listes dynamiques avec accès rapide par index |
| LinkedList                 | Liste doublement chaînée | Élevée               | Listes avec ajouts/suppressions fréquents     |

## Creation de notre premier tableau dynamique :

```java
package org.example;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // ici nous créons un tableau dynamique de strings
        // et on l'initialise
        //pouf un tableau apparait
        List<String> names = new ArrayList<>();
        //puis nous allons saisir le nom du tableau pour lui
        //AJOUTER ADD
        //une nouvelle valeur
        names.add("Alice");
        names.add("Bob");
        //on affiche le tableau qui contient nos deux valeurs initialisées
        System.out.println(names);
    }
}
```

### Sortie :

```
[Apple, Banana]
```

## Set (HashSet, TreeSet)

### Definiton

- Un Set stocke des éléments uniques.
- HashSet est rapide mais non ordonné,
- TreeSet maintient un ordre naturel ou personnalisé.

### BENCHMARK HASHSET TREESET

| Type de Set | Structure de Données    | Ordre des Éléments            | Performances                                 | Consommation Mémoire | Cas d'utilisation                             |
| ----------- | ----------------------- | ----------------------------- | -------------------------------------------- | -------------------- | --------------------------------------------- |
| HashSet     | Table de hachage        | Aucun                         | Rapide pour `add` et `contains` (O(1))       | Modérée              | Stockage rapide d'éléments uniques sans ordre |
| TreeSet     | Arbre binaire équilibré | Ordre naturel ou personnalisé | Moins rapide, `add` et `contains` (O(log n)) | Élevée               | Stockage ordonné d'éléments uniques           |

```java
package org.example;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // comme pour List<String> nous allons initier une liste
        // qui va etre stocké dans un Hashset cette fois
        Set<String> items = new HashSet<>();
        items.add("Apple");
        items.add("Banana");
        // le resultat est le même nous récupérons un tableau comme pour liste
        System.out.println(items);
    }
}
```

## Map (HashMap, TreeMap)

### Définition :

- Une Map associe des clés à des valeurs.
- HashMap est rapide mais non ordonné,
- TreeMap trie les clés.

```java
package org.example;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        //mise en place du hashmap comme dans les tableaux précédents on indique les types
        // dans des ancres <>
        // a la difference des List et des Set
        // Map accueille deux types
        // le premier est un Integer, le deuxieme un String
        // pour ajouter on utilise PUT au lieu de ADD pour map

        Map<Integer, String> users = new HashMap<>();
        users.put(1, "Alice");
        users.put(2, "Bob");
        System.out.println(users);
    }
}
```

l'output est different cette fois on ne renvois plus les valeurs dans un tableau mais dans un objet :

```
{1=Alice, 2=Bob}
```

## Utilisation des Generics

### Définition :

Les Generics permettent de définir le type d’éléments qu’une collection peut contenir, évitant les erreurs de type au moment de l’exécution.

```java
List<Integer> numbers = new ArrayList<>();
numbers.add(10);
numbers.add(20);
System.out.println(numbers);
```

### Comparaison avec et sans generique :

### Avec generique

- En spécifiant **String** dans les **chevrons** , nous rendons cette liste paramétrable avec le type de notre choix.

```java
package org.example;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>();
        names.add("Alice");
        names.add("Bob");
        System.out.println(names);
    }
}
```

### Sans generique

- Sans Generics, nous devons utiliser des conversions (casts) manuelles et risquer des erreurs :

```java
List names = new ArrayList(); // Sans Generics
names.add("Alice");
names.add(42); // Pas d'erreur ici !
String name = (String) names.get(1); // Erreur à l'exécution
```

![border](../assets/line/line-pink-point_r.png)

<a href="#missions">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
