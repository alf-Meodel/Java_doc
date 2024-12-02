 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# EXERCICES JAVA CODE WARS

![border](../assets/line/line-teal-point_l.png)

## Sommaire

- [Entête d'une méthode comprehension](#entête-dune-méthode-comprehension)
- [Exercice 1 tableaux](#exercice-1-les-tableaux)
- [Exercice 2 Modulo et fleurs](#exercice-2-une-histoire-de-fleurs-divisbles-par-2-ou-non)
- [Exercice 3 Nombre de pages \* nombre d'élèves](#exercice-3-nombre-de-pages-et-nombre-délèves)
- [Exercice 4 If b is boolean ](#exercice-4-if-boolean-is-b-yes-or-no)
- [Exercice 5 Convertir les heures](#exercice-5-convertir-les-heures)
- [Exercice 6 Supprimer les points d'exclamation avec REPLACE](#exercice-6-supprimer-tout-les-points-dexclamation-avec-replace)
- [Exercice 7 Une aiguille dans une botte de foin avec FOR](#exercice-7-une-aiguille-dans-une-botte-de-foin-avec-findneedle)
- [Exercice 8 Pierre feuille papier ciseaux ](#exercice-8-pierre-feuille-papier--ifs)
- [Exercice 9 location voiture réductions](#exercice-9-location-voiture-réductions)
- [Exercice 10 hydratation litre d'eau](#exercice-10-hydratation-litre-deau)
- [Exercice 11 si pair alors \* 8](#exercice-11-si-pair-alors--8)
- [Exercice 12 Quick fast](#exercice-12-quick-fast)
- [Exercice 13 Mission impossible](#exercice-13-mission-impossible)
- [Exercice 13 Foreach Moutons](#exercice-14-foreach-moutons)

![border](../assets/line/border_deco_rb.png)

# Entête d'une méthode comprehension

```java
public static int countSheeps(Boolean[] arrayOfSheeps) {
```

Exemple d’appel :

```java
int result = Counter.countSheeps(arrayOfSheeps);
```

![border](../assets/line/line-pink-point_l.png)

## Exemple d’utilisation

```java
public class Counter {
    public static int countSheeps(Boolean[] arrayOfSheeps) {
        if (arrayOfSheeps == null) {
            return 0; // Gérer le cas où l'entrée est nulle
        }

        int count = 0;
        for (Boolean sheep : arrayOfSheeps) {
            if (sheep != null && sheep) {
                count++;
            }
        }
        return count;
    }
}
```

## Appel de la méthode :

```java
public class Main {
    public static void main(String[] args) {
        Boolean[] sheeps = {true, true, false, null, true};
        int totalSheeps = Counter.countSheeps(sheeps);
        System.out.println("Nombre de moutons présents : " + totalSheeps);
    }
}
```

## Sortie attendue :

Nombre de moutons présents : 3

# Liste des exercices :

![border](../assets/line/line-pink-point_l.png)

## Exercice 1 les tableaux

Creation d'un tableau à partir d'une methode smash

```JAVA
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

```JAVA
public static String smash(String... words)
```

- Si nous déclarions une simple variable voila à quoi aurait ressemblé

```JAVA
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

```JAVA
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

```JAVA
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

### code de base

```JAVA
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

```JAVA
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

```JAVA
class Solution {
    static String removeExclamationMarks(String s) {

        // Remplace tous les '!' par une chaîne vide
        return s.replace("!", "");

}}
```

## Exercice 7 une aiguille dans une botte de foin avec findNeedle()

Pouvez-vous trouver l’aiguille dans la botte de foin ?
Écrivez une fonction findNeedle() qui prend un array
plein de déchets mais qui en contient un "needle"
Une fois que votre fonction a trouvé l'aiguille,
elle doit renvoyer un message (sous forme de chaîne) indiquant :
"found the needle at position "en plus index il a trouvé l'aiguille,

- Pour résoudre ce problème nous allons procéder ainsi :

- Nous décidons trouver un objet donc nosu allosn parcourir cete objet ; ici avec une **Boucle FOR** ; ainsi tant que la longueur totale de la botte de foin n'est pas parcourue **LENGTH**
- LE FOR DEMARRE à 0 et s'incremente jusqu'a atteindre la valeur max **LENGTH**

```JAVA
public class Kata {
    // Méthode pour trouver needle
    public static String findNeedle(Object[] haystack) {
        // Parcourir la motte de foin avec un for de 0 jusqu'a sa logueur max
        for (int i = 0; i < haystack.length; i++) {
          // compare la chaine de caractère needle et si elme est égale
         // à la position dans la motte de foin alors on retorune l'empalcement correspondant
            if ("needle".equals(haystack[i])) {
                return "found the needle at position " + i;
            }
        }
        // Si "needle" n'est pas trouvé (au cas où)
        return "needle not found";
    }

  public static void main(String[] args){
    // declarer le tableau

    Object[] haystack = {"hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"};
       // Appel de la méthode findNeedle qui applique sa boucle for
    //qui retourne sa position si les noms correspondent
        String resultat = findNeedle(haystack);
        System.out.println(resultat);
  }
}
```

## Exercice 8 Pierre feuille papier ... IF's

- Pierre-papier-ciseaux EN JAVA :
- Jouons ! Il faut retourner quel joueur a gagné ! En cas d'égalité retourner Draw!.

- NOus allons donc créer notre methode principale que nosu nommons RPS ; rock paper scissors qui fonctionne en paire donc possède deux types
- Puis nous allons mettre dans des ifs les differents cas possibles
- Ainsi nous allons écrire si l'option1 est égale à l'option2 et bien nosu allons recommencer ( égalité)
- Pusi ensuite nous allons lister les 3 cas de figures de victorie d'un des joueurs
- si les cas de figures ne se sont pas présentés l'auter joueur gagne
- psvm permet d'éprouevr noter méthode en donnant des combinaisons de valeurs

```JAVA
public class Kata {
    public static String rps(String choix1, String choix2) {
        if (choix1.equals(choix2)) return "Draw!";
        if ((choix1.equals("rock") && choix2.equals("scissors")) ||
            (choix1.equals("paper") && choix2.equals("rock")) ||
            (choix1.equals("scissors") && choix2.equals("paper"))) {
            return "Player 1 won!";
        }
        return "Player 2 won!";
    }

    public static void main(String[] args) {
        // Tests simples
        System.out.println(rps("scissors", "paper"));
        System.out.println(rps("scissors", "rock"));
        System.out.println(rps("paper", "paper"));
    }
}
```

## Exercice 9 Location voiture réductions

### Enoncé

Après un trimestre difficile au bureau, vous décidez de prendre des vacances pour vous reposer.

- Vous réservez donc un vol pour vous et votre petite amie et essayez de laisser tout ce désordre derrière vous.

- Pour vous déplacer pendant vos vacances, vous aurez besoin d'une voiture de location. Le responsable de la location de voiture vous fera de bonnes offres.

---

- Chaque jour de location de voiture coûte **40 $** .
- Si nous louons une voiture pendant 7 jours ou plus, nous bénéficions d'une réduction de **50 $** sur le total.
- Par ailleurs, si nous louons une voiture pendant 3 jours ou plus, nous bénéficions d'une réduction de **20 $** sur le total.

- **Objectif :** Écrire un code qui donne **le montant total pour différents jours (d).**

---

### Explications du code :

**d = nombre de jours**

- Calcul du coût total de base :

- **Dans un premier temps nous allons multiplier le nombre de jours d par 40** pour obtenir le coût de base.

- **Puis nous allons appliquer les réductions** :

  - Si **d >= 7**, nosu appliquons une réduction de 50 $.
  - Sinon, **si d >= 3**, appliquez une réduction de 20 $.

    **L'utilisation de else if garantit que seule la réduction la plus avantageuse est appliquée.**

- Retourner le montant total :

- Une fois les réductions appliquées, nous affichons le coût total.

### Code final :

```JAVA
public class Kata {
  public static int rentalCarCost(int d) {
//     d = nombre de jours

   int total =  d * 40;

     //Appliquer les reductions

     if ( d >= 7){
       total -= 50;
     }else if (d >= 3){
       total -= 20;
     }

    return total;


  }
}
```

## Exercice 10 hydratation litre d'eau

- Nathan adore faire du vélo.

Parce que Nathan sait qu’il est important de rester hydraté, il boit 0,5 litre d’eau par heure de vélo.

On vous donne le temps en heures et vous devez renvoyer le nombre de litres que Nathan boira, arrondi à la plus petite valeur.

### Traduction en code :

0,5 for one hour ( 60 minutes)

##### Comprendre les règles :

Nathan boit **0,5 litre d'eau par heure de vélo**.
Le temps passé à faire du vélo est donné en heures (time).
Le résultat doit être arrondi à la plus petite valeur **(fonction floor en mathématiques).**

##### Entrée :

Une valeur numérique représentant le temps passé en heures (peut être décimal).

##### Sortie :

Un entier représentant le nombre de litres d'eau que Nathan boira.

#### Plan pour écrire le code :

Multipliez le temps (time) par 0,5 pour calculer les litres.
Utilisez la fonction Math.floor() pour arrondir à la plus petite valeur.
Retournez le résultat en entier.

```JAVA
public class KeepHydrated {
    // Méthode pour calculer la quantité d'eau que nathan va boire
    public static int Liters(double time) {
        //Nous multiplions par 0,5 en arrondissant
      //Le (int) entre parenthèses est une conversion explicite (appelée aussi cast en Java).
      //Cela signifie que nous transformons une valeur d'un type (ici double en int).
        return (int) Math.floor(time * 0.5);
    }
}
```

## Exercice 11 si pair alors \* 8

Ce kata consiste à multiplier un nombre donné par huit s'il s'agit d'un nombre pair et par neuf sinon.

- Méthode pour traduire en code :

- Nous allons déterminer dans un if si le nombre est pair ou imparaire
- Puis nous allons le multiplier par huit si il est pair

```JAVA
public class Sid {
    public static int simpleMultiplication(int n) {
      // Condition en ternaire
      //(condition) ? valeur_si_vrai : sinon valeur_si_faux;
           return (n % 2 == 0) ? n * 8 : n * 9;
    }
}
```

## Exercice 12 quick fast

Codez aussi vite que vous le pouvez ! Vous devez doubler l'entier et le renvoyer.

```JAVA
class Java {
  public static int doubleInteger(int i) {
   i = i *2;
    return i;
  }
}
```

## Exercice 13 mission impossible

Bienvenue. Dans ce kata, on vous demande de mettre au carré chaque chiffre d'un nombre et de les concaténer.

Par exemple, si nous exécutons 9119 via la fonction, nous obtiendrons 811181, car 9 2 est 81 et 1 2 est 1. (81-1-1-81)

Exemple n°2 : une entrée de 765 renverra/devra renvoyer 493 625 car 7 2 est 49, 6 2 est 36 et 5 2 est 25. (49-36-25)

Remarque : la fonction accepte un entier et renvoie un entier.

#### Traduire le problème

**Entrée :** Un entier n (par exemple, 9119).

**Processus :**
Convertir l'entier en une chaîne pour traiter chaque chiffre séparément.
Mettre au carré chaque chiffre.
Concaténer les carrés en une nouvelle chaîne.
Convertir cette chaîne en entier.

**Sortie :** Un entier résultant de la concaténation des carrés des chiffres.

```JAVA
public class SquareDigit {

    // Méthode qui prend un entier `n` en entrée, par exemple 9119
    public static int squareDigits(int n) {
        // Convertir l'entier en chaîne de caractères pour accéder à chaque chiffre individuellement
        // Exemple : Si n = 9119, alors number = "9119"
        String number = Integer.toString(n);

        // Utilisation de StringBuilder pour construire efficacement une nouvelle chaîne
        // qui contiendra les carrés de chaque chiffre concaténés
        StringBuilder result = new StringBuilder();

        // Parcourir chaque caractère de la chaîne `number`
        for (char c : number.toCharArray()) {
            // Convertir le caractère en entier
            // Exemple : '9' devient 9
            int digit = Character.getNumericValue(c);

            // Calculer le carré du chiffre et l'ajouter à la chaîne result
            // Exemple : si digit = 9, alors digit * digit = 81, et "81" est ajouté à result
            result.append(digit * digit);
        }

        // Convertir la chaîne résultante (contenant les carrés concaténés) en entier
        // Exemple : si result = "811181", alors Integer.parseInt("811181") retourne 811181
        return Integer.parseInt(result.toString());
    }
}
```

## Exercice 14 FOREACH Moutons

### Enoncé :

Considérons un tableau/une liste de moutons dans lesquels certains moutons peuvent manquer à leur place. Nous avons besoin d'une fonction **qui compte le nombre de moutons présents** dans le tableau (vrai signifie présent).

### Par exemple :

```JAVA
[true,  true,  true,  false,
  true,  true,  true,  true ,
  true,  false, true,  false,
  true,  false, false, true ,
  true,  true,  true,  true ,
  false, false, true,  true]
```

La bonne réponse serait 17 (true).

### Décomposer les tâches

- Parcourir le tableau des moutons.
- Vérifier si chaque élément représente un mouton présent (true).
- Gérer les cas où les éléments peuvent être null (valeur manquante).
- Compter les moutons valides (ceux qui sont true).
- Retourner le total.

### Traduire chaque tâche en code

1. Parcourir le tableau
   En Java, nous utilisons une boucle for-each pour parcourir un tableau

```java
for (Boolean sheep : arrayOfSheeps) {
// Code à exécuter pour chaque mouton
}
```

2. Vérifier si le mouton est présent
   Nous devons vérifier deux choses pour chaque élément du tableau :

- Que l'élément n'est pas null.
- Que l'élément est égal à true

```JAVA
if (sheep != null && sheep) {
    // Mouton présent
}
```

### Compter les moutons valides

Pour compter les moutons présents, nous utilisons une variable count que nous incrémentons chaque fois qu'un mouton valide est trouvé :

```java
int count = 0;
for (Boolean sheep : arrayOfSheeps) {
    if (sheep != null && sheep) {
        count++;
    }
}
```

### Retourner le total

Une fois la boucle terminée, nous retournons la valeur de count :

```java
return count;
```

### CODE :

```java
public class Counter {
    public static int countSheeps(Boolean[] arrayOfSheeps) {
        // Initialiser le compteur
        int count = 0;

        // Parcourir chaque élément du tableau
        for (Boolean sheep : arrayOfSheeps) {
            // Vérifier si le mouton est présent
            if (sheep != null && sheep) {
                count++;
            }
        }

        // Retourner le total des moutons présents
        return count;
    }
}
```

### Tester le code :

```java
public class Main {
    public static void main(String[] args) {
        Boolean[] sheeps = {
            true, true, true, false,
            true, true, null, true,
            false, null, true, false
        };

        int result = Counter.countSheeps(sheeps);
        System.out.println("Nombre de moutons présents : " + result); // Devrait afficher 6
    }
}
```

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
