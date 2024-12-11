 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# Collections et Gestion des Exceptions

![border](../assets/line/line-pink-point_l.png)

```
 Lever une exception signifie signaler qu’un problème est survenu pendant l’exécution du programme
```

## Missions

- [ ] [Découvrir les Collections Java]()

  - [ ] [List (ArrayList, LinkedList)](#les-collections-list-arraylist-linkedlist)
  - [ ] [Set (HashSet, TreeSet)](#set-hashset-treeset)
  - [ ] [Map (HashMap, TreeMap)](#map-hashmap-treemap)
  - [ ] [Utilisation des Generics](#utilisation-des-generics)

- [ ] [Gérer les exceptions](#gérer-les-exceptions)

  - [ ] [Utilisation de try-catch-finally](#utilisation-de-try-catch-finally)
  - [ ] [Propagation des exceptions avec throws](#propagation-des-exceptions-avec-throws)
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

![border](../assets/line/line-teal-point_l.png)

## Les Collections List (ArrayList, LinkedList)

### Définition :

- Une **List** est une collection ordonnée qui permet des éléments dupliqués.
- **ArrayList** est rapide pour les accès,
- **LinkedList** est plus efficace pour les modifications.

### Benchmark ARRAYLIST LINKEDLIST:

---

| Type de Tableau/Collection | Structure de Données     | Consommation Mémoire | Cas d'utilisation                             |
| -------------------------- | ------------------------ | -------------------- | --------------------------------------------- |
| Array (Tableau simple)     | Tableau statique         | Faible               | Manipulations simples avec taille fixe        |
| ArrayList                  | Tableau dynamique        | Modérée              | Listes dynamiques avec accès rapide par index |
| LinkedList                 | Liste doublement chaînée | Élevée               | Listes avec ajouts/suppressions fréquents     |

---

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

![border](../assets/line/line-teal-point_l.png)

## Set (HashSet, TreeSet)

### Definiton

- Un Set stocke des éléments uniques.
- HashSet est rapide mais non ordonné,
- TreeSet maintient un ordre naturel ou personnalisé.

### BENCHMARK HASHSET TREESET

---

| Type de Set | Structure de Données    | Ordre des Éléments            | Performances                                 | Consommation Mémoire | Cas d'utilisation                             |
| ----------- | ----------------------- | ----------------------------- | -------------------------------------------- | -------------------- | --------------------------------------------- |
| HashSet     | Table de hachage        | Aucun                         | Rapide pour `add` et `contains` (O(1))       | Modérée              | Stockage rapide d'éléments uniques sans ordre |
| TreeSet     | Arbre binaire équilibré | Ordre naturel ou personnalisé | Moins rapide, `add` et `contains` (O(log n)) | Élevée               | Stockage ordonné d'éléments uniques           |

---

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

![border](../assets/line/line-teal-point_l.png)

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

![border](../assets/line/line-teal-point_l.png)

# Gérer les Exceptions

## Utilisation de try-catch-finally

### Définition :

- Gérer les exceptions en **encapsulant le code susceptible d’échouer dans un bloc try**,
- traiter les erreurs dans un catch, **et exécuter du code dans finally si nécessaire.**

```java
package org.example;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // le Bloc try :
        // le code susceptible de générer une exception est placé ici
        try {
            // Une division par zéro est tentée ici ( qui pose evidemment problème)
            int result = 10 / 0;
        }
        // Bloc catch : il intercepte l'exception si elle survient
        catch (ArithmeticException e) {
            // e.getMessage() est une méthode de la classe Throwable
            // Elle renvoie un message descriptif de l'exception déclenchée.
            // Dans ce cas, elle retourne : "/ by zero" (erreur spécifique à la division par zéro).
            System.out.println("Erreur : " + e.getMessage());
        }
        // Bloc finally : ce code s'exécute toujours, qu'une exception ait été levée ou non.
        finally {
            System.out.println("Fin du traitement.");
        }
    }
}
```

![border](../assets/line/line-teal-point_l.png)

## Ce qui se passe

### Bloc try :

- Le code dans ce bloc tente de diviser 10 par 0.
- En Java, une division par zéro pour des entiers **déclenche une exception de type ArithmeticException.**

### Bloc catch :

- Quand l'exception est levée, **le programme saute directement au bloc catch.**
- L'objet **e** est une **instance de ArithmeticException** qui contient des informations sur l'erreur.

### e.getMessage() :

- C'est une méthode héritée de la classe Throwable (la classe parent de toutes les exceptions en Java).
- Elle retourne un message descriptif de l'exception. Dans ce cas précis, elle renverra la chaîne : "/ by zero".
- Cela permet de comprendre la nature exacte de l'erreur.

### Bloc finally :

- Ce bloc est exécuté dans tous les cas, que l'exception ait été levée ou non.
- Il est souvent utilisé pour des opérations de nettoyage (comme fermer un fichier ou libérer des ressources).

## D'autres types d'exceptions :

- **ArithmeticException** : Utilisée pour les erreurs mathématiques, comme une division par zéro.
- **NullPointerException** : Levée lorsque tu tentes d’accéder à un objet qui est null.
- **IOException** : Utilisée pour les erreurs d’entrée/sortie (lecture/écriture de fichiers, flux, etc.).
- **ArrayIndexOutOfBoundsException** : Levée lorsque tu accèdes à un index invalide dans un tableau.

![border](../assets/line/line-teal-point_l.png)

## Propagation des exceptions avec throws

### Définition :

Permet à une méthode de propager une exception à son appelant en utilisant le mot-clé throws.

```java
package org.example;
import java.nio.file.*;
import java.nio.file.*;    // Import des classes nécessaires pour manipuler des fichiers et chemins
public class Main {
    public static void main(String[] args) {
        try {
            // Appelle une méthode qui est enveloppé dans le try
            // pour réagir si une erreur se produit on lui
            // ACCORDE UN THROW
            // pour indiquer qu'elle peut LEVER UNE EXCEPTION
            // qui se déclenche si une anomalie est detectée
            // Si une erreur est avéré nuisant au bon focntionnement de la methode
            // alors le message de l'erreur correspondant
            // au type d'exception ici ArithmeticException
            // et envoyé dans le catch
            // qui va récupérer le message d'erreur correspondant
            divide(10, 0);
        } catch (ArithmeticException e) {
            // Capture et affiche le message de l'exception
            System.out.println("Erreur capturée : " + e.getMessage());
        }
    }

    // Méthode qui effectue une division et peut lever une exception
    static void divide(int a, int b) throws ArithmeticException {
        // Si 'b' est 0, une exception sera levée
        int result = a / b;
        System.out.println("Résultat : " + result);
    }
}
```

![border](../assets/line/line-pink-point_r.png)

<a href="#missions">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
