 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# EXERCICES JAVA CODE WARS

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Exercice 1 tableaux](#exercice-1)
- [Exercice 2 Modulo et fleurs](#exercice-1)

![border](../assets/line/border_deco_rb.png)

# Liste des exercices :

![border](../assets/line/line-pink-point_l.png)

## Exercice 1

Creation d'un tableau à partir d'une methode smash

```
public class SmashWords {

    public static String smash(String... words) {
        // Vérifie si le tableau est vide ou null
        if (words == null || words.length == 0) {
            return "";
        }

        // Utilise String.join pour assembler les mots avec un espace
        return String.join(" ", words);
    }

    public static void main(String[] args) {
        // Exemple d'utilisation
        String[] testWords = {"this", "is", "a", "new", "test"};
        System.out.println(smash(testWords)); // Affiche : "this is a test"
    }
}
```

### Explication :

- La variable word est déclarée de la manière suivante pour définir un tableau ou une chaine de caractères:

```
public static String smash(String... words)
```

- Si nous déclarions une simple variable voila à quoi aurait ressemblé

```
public static String smash(String word) { ... }
smash("hello");
```

- **public class SmashWords :** Définit une classe publique nommée SmashWords.

- **public static String smash(String... words) :** Déclare une méthode statique qui accepte un nombre variable d'arguments String (convertis en tableau words) et retourne une chaîne.

- **if (words == null || words.length == 0) :** Vérifie si words est nul ou vide. Si vrai, retourne une chaîne vide "".

- **return String.join(" ", words); :** Utilise la méthode Java String.join pour assembler les mots en une phrase avec un espace entre eux.

- **public static void main(String[] args) :** Définit la méthode principale pour exécuter le programme.

- **String[] testWords = {"this", "is", "a", "new", "test"}; :** Déclare un tableau contenant des mots.

- **System.out.println(smash(testWords)); :** Appelle smash avec le tableau et affiche la phrase this is a new test.

![border](../assets/line/line-pink-point_r.png)

## Exercice 2

Timmy et Sarah pensent qu'ils sont amoureux, mais là où ils vivent, ils ne le sauront qu'une fois qu'ils auront chacun cueilli une fleur. Si l'une des fleurs a un nombre pair de pétales et l'autre un nombre impair de pétales, cela signifie qu'ils sont amoureux.

Écrivez une fonction qui prendra le nombre de pétales de chaque fleur et renverra vrai s'ils sont amoureux et faux s'ils ne le sont pas.

### Analyse simple de l'énoncé :

Un nombre est pair s'il est divisible par 2 (par exemple, 4 % 2 == 0).
Un nombre est impair s'il ne l'est pas (par exemple, 5 % 2 != 0).
Pour que l'amour soit confirmé :
Un nombre doit être pair ET l'autre impair, ou inversement.

### En termes logiques :

Si (flower1 % 2 == 0) et (flower2 % 2 != 0), alors ils sont amoureux.
Sinon, si (flower1 % 2 != 0) et (flower2 % 2 == 0), ils le sont aussi.

### Resolution

```
public class OppositesAttract {

  public static boolean isLove(final int flower1, final int flower2) {
//Donc si flower peut etre divisé par deux alors il est pair
//et si Flower ne peut etre divisé par 2 alors i lest impair
//  ET INVERSEMENT
// Si dans l'auter sens m'un des deux à une valeur pair ou impair

    return (flower1 % 2 == 0 && flower2 % 2 != 0) || (flower1 % 2 != 0 && flower2 % 2 == 0);
  }
  public static void main (String[] args){
  System.out.println(isLove(4,7));
      System.out.println(isLove(6,2));
}}
```

## Exercice 2

### Enoncé

Tes camarades de classe t'ont demandé de leur copier des documents. Tu sais qu'il y a "n" camarades de classe et que les documents ont "m" pages.

Votre tâche consiste à calculer le nombre de pages vierges dont vous avez besoin. Si n < 0ou m < 0 renvoie 0.

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
