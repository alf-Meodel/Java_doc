 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# EXERCICES JAVA CODE WARS

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Exercice 1 tableaux](#exercice-1-les-tableaux)
- [Exercice 2 Modulo et fleurs](#exercice-2-une-histoire-de-fleurs-divisbles-par-2-ou-non)
- [Exercice 3 Nombre de pages \* nombre d'élèves](#exercice-3-nombre-de-pages-et-nombre-délèves)
- [Exercice 4 If b is boolean ](#exercice-4-if-boolean-is-b-yes-or-no)
- [Exercice 5 Convertir les heures](#exercice-5-convertir-les-heures)
- [Exercice 6 Supprimer les points d'exclamation](#exercice-6-supprimer-tout-les-points-dexclamation-avec-replace)

![border](../assets/line/border_deco_rb.png)

# Liste des exercices :

![border](../assets/line/line-pink-point_l.png)

## Exercice 1 les tableaux

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

## Exercice 2 une histoire de fleurs divisbles par 2 ou non

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

## Exercice 3 nombre de pages et nombre d'élèves

### Enoncé

Tes camarades de classe t'ont demandé de leur copier des documents. Tu sais qu'il y a "n" camarades de classe et que les documents ont "m" pages.

Votre tâche consiste à calculer le nombre de pages vierges dont vous avez besoin. Si n < 0 ou m < 0 renvoie 0.

### Code :

```
public class Paper
{
  public static int paperWork(int n, int m)
  {
    // Dans un premier temps nous allons vérifier si n ou m sont des valeurs invalides
    if (n < 0 || m < 0){
      return 0;
    }

    return n * m;
  }
}
```

## Exercice 4 if boolean is b yes or no

Complétez la méthode qui prend une valeur booléenne et renvoie une "Yes"chaîne pour true, ou une "No"chaîne pour false.

### code de base

```
class YesOrNo {
    public static String boolToWord(boolean b) {
        if (b) {
            return "Yes";
        } else {
            return "No";
        }
    }
}
```

## Exercice 5 convertir les heures

### Énoncé

L'horloge indique h les heures, m les minutes et s les secondes après minuit.

Votre tâche consiste à écrire une fonction qui renvoie le temps écoulé depuis minuit en millisecondes.

### Methode :

- Pour résoudre cet exercice, nous devons convertir les heures, minutes et secondes en millisecondes et retourner le résultat. Voici une solution simple et claire :

```
{
  public static int Past(int h, int m, int s)
  {
    // Conversion en millisecodne

    int heureEnMillisecondes =  h * 60 * 60 * 1000;
      int minutesEnMillisecondes = m * 60 * 1000;
      int secondesEnMillisecondes = s * 1000;

      // Somme des millisecondes
      return heureEnMillisecondes + minutesEnMillisecondes + secondesEnMillisecondes;
  }
}
```

## Exercice 6 Supprimer tout les points d'exclamation avec replace

### Enoncé

```
class Solution {
    static String removeExclamationMarks(String s) {

        // Remplace tous les '!' par une chaîne vide
        return s.replace("!", "");

}}
```

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
