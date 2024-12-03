 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# DOC TYPE

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Difference entre stringBuilder](#différence-entre-stringbuilder-et-string)
- [Difference entre stringBuilder](#différence-entre-stringbuilder-et-string)

![border](../assets/line/border_deco_rb.png)

# Strings

![border](../assets/line/line-pink-point_r.png)

## Différence entre StringBuilder et String

### String :

- **Immuable :** Une fois créé, son contenu ne peut pas être modifié.
  Méthodes comme substring, indexOf, ou length permettent d'accéder à son contenu sans le modifier.

### StringBuilder :

- **Modifiable (mutable) :** Son contenu peut être modifié directement.
  Méthodes spécifiques comme append, reverse, insert, et delete sont conçues pour manipuler les chaînes efficacement.

```java
public class Main {
public static void main(String[] args) {
// Chaîne d'entrée
String phrase = "Bonjour, ceci est une phrase. {Avec quelques caractères spéciaux}/";

// Supprimer les caractères avec split()
String[] mots = phrase.split("[.,{}\\\\/]+");

// Reconstituer la phrase sans les délimiteurs
String resultat = String.join(" ", mots);

// Afficher le résultat
System.out.println(resultat);
    }
}
```

## Split() ou comment nettoyer un chaine de caractère

### Définition :

La méthode split() divise une chaîne en supprimant les délimiteurs spécifiés via une regex (ex. [.,{}\\/]+). Les éléments correspondants sont remplacés par des séparations, retournant un tableau des morceaux restants.

- Cas d'utilisation :

```java
public class Main {
    public static void main(String[] args) {
        // Chaîne d'entrée
        String phrase = "Bonjour, ceci est une phrase. {Avec quelques caractères spéciaux}/";
        // Supprimer les caractères avec split()
        String[] mots = phrase.split("[.,{}\\\\/]+");
        // Reconstituer la phrase sans les délimiteurs
        String resultat = String.join(" ", mots);
        // Afficher le résultat
        System.out.println(resultat);
    }
}
```

### StringBuilder : Append

append() est une méthode de la classe StringBuilder (ou StringBuffer). Elle permet d'ajouter du contenu à la fin d'une chaîne existante sans recréer un nouvel objet, contrairement à la concaténation avec +.

### Exemple :

```
StringBuilder sb = new StringBuilder("Bonjour");
sb.append(" le monde"); // Ajoute " le monde"
System.out.println(sb.toString()); // Affiche : "Bonjour le monde"
```

![border](../assets/line/line-pink-point_r.png)

<a href="#sommaire"> <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;"></a>

![border](../assets/line/border_deco_l.png)
