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
- [Exercice 14 Foreach Moutons](#exercice-14-foreach-moutons)
- [Exercice 15 les-fameux-amis-à-4-lettres](#exercice-15-les-fameux-amis-à-4-lettres)
- [Exercice 16 distributeur-de-4-à-6-billets](#exercice-16-distributeur-de-4-à-6-billets)
- [Exercice 17 exercice-17-convertisseur](#exercice-17-convertisseur)
- [Exercice 18 transformer-une-chaine-en-un-nombre](#exercice-18-transformer-une-chaine-en-un-nombre)
- [Exercice 19 convertir-en-binaire](#exercice-19-convertir-en-binaire)
- [Exercice 20 supprime-le-premier-et-le-dernier-caractère](#exercice-20-supprime-le-premier-et-le-dernier-caractère)
- [Exercice 21 tableau-inversé](#exercice-21-tableau-inversé)
- [Exercice 22](#exercice-22)

## Méthodes utilisées

- [Value Of : transformer un int en string ](#valueof-)
- [Integer.parseInt(): chaine en nombre ](#integerparseint-)
- [To Binary String: Chaine en binaire](#tobinarystring-)
- [Str.Substring ](#strsubstring)
- [CharAt: renvoie le caractère à la position indiqué](#charat)
- [Substring: exemple 2 ](#substring-explication-2-)
- [Replace: espace par des espaces vides ](#replace)
- [Cast with (long) a hunting dragon story ](#cast-with-long)
- [Cast with (long ](#cast-with-long)
- [Cast with méthode-arrayssortnumbers- ](#méthode-arrayssortnumbers-)
- [StringBuilder pour manipuler des chaînes dynamiques](#stringbuilder-pour-manipuler-des-chaînes-dynamiques)
- [Difference entre stringBuilder et String](#différence-entre-stringbuilder-et-string)
- [Split ou comment retirer le elements d'une phrase](#retirer)
- [Append pour rajoter des caractères à la suite ](#append--pour-rajouter-des-caractères-à-la-suite)

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

## Exercice 15, les fameux amis à 4 lettres

Créez un programme qui **filtre une liste de chaînes** et **renvoie une liste contenant uniquement le nom de vos amis**.

- Si un nom contient exactement **4 lettres**, vous pouvez être sûr qu'il s'agit d'un de vos **amis** !

- Sinon, vous pouvez être sûr qu'il ne s'agit pas...

```java
Input = ["Ryan", "Kieran", "Jason", "Yous"]
Output = ["Ryan", "Yous"]**

Input = ["Peter", "Stephen", "Joe"]
Output = []**
```

- Les chaînes d'entrée ne contiendront que des lettres.

Remarque : conservez l'ordre d'origine des noms dans la sortie.

### Ce que l'énoncé demande :

- Vous avez une liste de chaînes (des noms).
- Vous devez filtrer cette liste pour ne garder que les noms qui contiennent exactement 4 lettres.
- Vous devez conserver l'ordre d'origine dans la liste filtrée.
- Si aucun nom ne correspond, la liste de sortie sera vide.

### Découpage en étapes simples :

- Parcourir la liste des noms donnée en entrée.
- Vérifier pour chaque nom si sa longueur est égale à 4.
- Ajouter les noms qui respectent cette condition dans une nouvelle liste.
- Retourner la liste contenant uniquement les noms valides.

## Code :

```java
import java.util.ArrayList;
import java.util.List;

class Kata {
    public static List<String> friend(List<String> x) {
        // Liste pour stocker les noms filtrés
        List<String> friends = new ArrayList<>();

        // Parcourir chaque nom dans la liste d'entrée
        for (String name : x) {
            // Vérifier si le nom contient exactement 4 lettres
            if (name.length() == 4) {
                friends.add(name); // Ajouter le nom à la liste filtrée
            }
        }

        // Retourner la liste contenant uniquement les noms valides
        return friends;
    }
}
```

## Exercice 16 distributeur de 4 à 6 billets

Les distributeurs automatiques de billets autorisent les codes PIN à 4 ou 6 chiffres et les codes PIN ne peuvent contenir que 4 ou 6 chiffres exactement .

Si une chaîne PIN valide est transmise à la fonction, renvoyez true, sinon renvoyez false.

### Étapes de validation :

Vérifier si la longueur de la chaîne est exactement 4 ou 6.
Vérifier si tous les caractères de la chaîne sont des chiffres.

```java
public class Solution {

  public static boolean validatePin(String pin) {
    // Vérifier si la longueur est 4 ou 6
    if (pin.length() != 4 && pin.length() != 6) {
      return false;
    }

    // Vérifier si tous les caractères sont des chiffres
    for (char character_verification : pin.toCharArray()) {
      if (!Character.isDigit(character_verification)) {
        return false;
      }
    }

    // Si toutes les vérifications passent, retourner true
    return true;
  }
}
```

## Exercice 17 Convertisseur

## ValueOF :

- String.valueOf() convertit un type primitif ou un objet en chaîne. Pour les primitifs, il utilise la méthode de conversion appropriée (ex.: Integer.toString). Pour les objets, il retourne obj.toString() ou "null".

```java
class Kata {
  public static String numberToString(int num) {

    // POur retourner un string à partir d'une valeur int nosu allons convertir avec String = la valeur souhaité
    // valueOf = le convertisseur
     return String.valueOf(num);

  }
}
```

- Et pour ce resultat nous allons l'éprouver sur **une variable int** poru afficher le resultat

```java
public static void main (String[] args){
    int number = 123;
   System.out.println(numberToString(number));
  }
```

## Exercice 18 transformer une chaine en un nombre

### Integer.parseInt() :

**Integer.parseInt(str)** convertit une chaîne en entier. Elle analyse le texte dans str pour produire un type int. Si str n'est pas une chaîne valide (ex.: "abc"), elle lève une NumberFormatException. Cette méthode est utile pour gérer des entrées numériques sous forme de texte. Exemple : return Integer.parseInt("123"); retourne 123.

### Énoncé :

Nous avons besoin d'une fonction qui peut transformer une chaîne en un nombre. Quelles méthodes connaissez-vous pour y parvenir ?

Remarque : ne vous inquiétez pas, toutes les entrées seront des chaînes et chaque chaîne est une représentation parfaitement valide d'un nombre entier.

```java
Exemples
"1234" --> 1234
"605"  --> 605
"1405" --> 1405
"-7" --> -7
```

### Code :

```java
public class StringToNumber {
  public static int stringToNumber(String str) {
    return Integer.parseInt(str);
  }

  public static void main (String[] args){
    System.out.println(stringToNumber("1235"));
  }
}
```

## Exercice 19 convertir en binaire

### toBinaryString :

Integer.toBinaryString(int) convertit un entier en sa représentation binaire sous forme de chaîne. Par exemple, Integer.toBinaryString(5) retourne "101". Utile pour travailler avec des nombres en binaire sans manipuler des bits directement.

#### Consignes :

Implémentez une **fonction qui additionne deux nombres et renvoie leur somme en binaire**. La conversion peut être effectuée avant ou après l'addition.

**Le nombre binaire renvoyé doit être une chaîne.**

Exemples : (Entrée 1, Entrée 2 --> Sortie (explication)))

1, 1 --> "10" (1 + 1 = 2 in decimal or 10 in binary)
5, 9 --> "1110" (5 + 9 = 14 in decimal or 1110 in binary)

```java
public class Kata{

  public static String binaryAddition(int a, int b){
    //nous allons directement utiliser nos deu variables avec toBinaryString
    return Integer.toBinaryString(a + b);
  }
}
```

## Exercice 20 Supprime le premier et le dernier caractère

#### Consigne :

C'est assez simple. Votre objectif est de créer une fonction qui supprime le premier et le dernier caractère d'une chaîne. Vous disposez d'un seul paramètre, la chaîne d'origine. Vous n'avez pas à vous soucier des chaînes contenant moins de deux caractères.

### str.substring()

- str.substring(beginIndex, endIndex)
- extrait une sous-chaîne de str
- allant de beginIndex (inclus) à endIndex (exclus).
- beginIndex spécifie où commencer,
- et endIndex où s'arrêter.

```java

   public class RemoveChars {
    public static String remove (String str){
      return str.substring(1, str.length() - 1);
    }

    public static void main (String[] args){
      System.out.println(remove("Youpi"))
    }
   }
```

## Exercice 21 Tableau inversé

### CharAt

La méthode charAt() renvoie une nouvelle chaîne contenant le caractère (ou, plus précisément, le point de code UTF-16) à la position indiquée en argument.

```java
const sentence = 'The quick brown fox jumps over the lazy dog.';
const index = 4;
console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// Expected output: "The character at index 4 is q"
```

### Consignes

Convertir un nombre en tableau inversé de chiffres
Étant donné un nombre aléatoire non négatif, vous devez renvoyer les chiffres de ce nombre dans un tableau dans l'ordre inverse.

Exemple (entrée => sortie) :
35231 => [1,3,2,5,3]
0 => [0]

```java
public class Kata {
    public static int[] digitize(long n) {
        // Convertir le nombre en chaîne
        String nombreEnChaine = Long.toString(n);
        // Créer un tableau pour stocker les résultats
        int[] result = new int[nombreEnChaine.length()];

        // Parcourir les caractères de la chaîne de la fin au début
        for (int i = 0; i < nombreEnChaine.length(); i++) {
            // Extraire les chiffres en commençant par la fin
            result[i] = nombreEnChaine.charAt(nombreEnChaine.length() - 1 - i) - '0';
        }
        return result;
    }
    public static void main(String[] args) {
        // Test cases
        System.out.println(java.util.Arrays.toString(digitize(35231))); // [1, 3, 2, 5, 3]
        System.out.println(java.util.Arrays.toString(digitize(0)));     // [0]
    }
}
```

# Exercice 22

### Substring explication 2 :

La méthode substring() retourne une sous-chaîne de la chaîne courante, entre un indice de début et un indice de fin.

### Consignes

On va vous donner une chaîne non vide . Votre tâche consiste à **renvoyer le(s) caractère(s) du milieu de la chaîne**.

Si la longueur de la chaîne **est impaire**, renvoie le caractère du milieu.
Si la longueur de la chaîne **est paire**, renvoie les 2 caractères du milieu.

### Exemples :

- "test" --> "es"
- "testing" --> "t"
- "middle" --> "dd"
- "A" --> "A"

### Code

```java
public class Kata {
    public static String getMiddle(String mot) {
        // Calculer la longueur totale du mot
        int longueur = mot.length();
        // Déterminer l'indice central
        int milieu = longueur / 2;
        // Vérifier si la longueur du mot est paire ou impaire
        if (longueur % 2 == 0) {
            // Si la longueur est paire, retourner les deux caractères centraux
            return mot.substring(milieu - 1, milieu + 1);
        } else {
            // Si la longueur est impaire, retourner le caractère central
            return mot.substring(milieu, milieu + 1);
        }
    }
    public static void main(String[] args) {
        // Exemples de tests
        System.out.println(getMiddle("test"));     // "es" : deux caractères centraux
        System.out.println(getMiddle("testing")); // "t" : caractère central
        System.out.println(getMiddle("middle"));  // "dd" : deux caractères centraux
        System.out.println(getMiddle("A"));       // "A" : seul caractère
    }
}
```

# Exercice 23 si pair Even sinon Odd

### Consignes :

Créez une fonction qui prend un entier comme argument et renvoie "Even"pour les nombres pairs ou "Odd"pour les nombres impairs.

### Traduction du problème en code :

#### Qu'est-ce qu'un nombre pair ?

Un nombre est pair s'il est divisible par 2 sans reste.
Exemple : 4 % 2 == 0, donc 4 est pair.

#### Qu'est-ce qu'un nombre impair ?

Un nombre est impair s'il n'est pas divisible par 2 sans reste.
Exemple : 5 % 2 != 0, donc 5 est impair.

#### Comment utiliser ces règles dans le code ?

En utilisant l'opérateur modulo %, qui retourne le reste d'une division.
Si number % 2 == 0, alors le nombre est pair.
Sinon, il est impair.

### Code :

```java
public class Kata {
    public static String evenOrOdd(int number) {
        // Vérifier si le nombre est pair ou impair
        if (number % 2 == 0) {
            return "Even"; // Pair
        } else {
            return "Odd";  // Impair
        }
    }
    public static void main(String[] args) {
        // Exemples de test
        System.out.println(evenOrOdd(4));  // "Even"
        System.out.println(evenOrOdd(7));  // "Odd"
        System.out.println(evenOrOdd(0));  // "Even"
        System.out.println(evenOrOdd(-3)); // "Odd"
    }
}
```

# Exercice 24 Suppression des espaces

### REPLACE

La méthode replace() renvoie une nouvelle chaîne de caractères dans laquelle tout ou partie des correspondances à un modèle sont remplacées par un remplacement.

#### Consigne

Écrivez une fonction qui supprime les espaces de la chaîne, puis renvoie la chaîne résultante.

#### Exemples ( Entrée -> Sortie ) :

```
"8 j 8   mBliB8g  imjB8B8  jl  B" -> "8j8mBliB8gimjB8B8jlB"
"8 8 Bi fk8h B 8 BB8B B B  B888 c hl8 BhB fd" -> "88Bifk8hB8BB8BBBB888chl8BhBfd"
"8aaaaa dddd r     " -> "8aaaaaddddr"
```

### CODE :

```

public class Kata {
    public static String noSpace(final String x) {
        return x.replace(" ", "");
    }
  public static void main (String[] args){
    System.out.println(noSpace("lo l o lo g h  g f "));
  }
}

```

# Exercice 25 Hero et Dragon :

### Cast with (long)

Le (long) force la conversion de dragons en type long, qui peut gérer des valeurs plus grandes qu'un int. Sans cela, dragons _ 2 reste un int et dépasse la limite maximale (2,147,483,647). Avec (long) dragons _ 2, le calcul se fait correctement sans débordement.

### Consignes

Un héros est en route vers le château pour accomplir sa mission.
Cependant, on lui a dit que le château est entouré de quelques dragons puissants !

- **Chaque dragon nécessite 2 balles** pour être vaincu,
- notre héros n'a aucune idée du nombre de balles qu'il doit transporter.
- En supposant qu'il va récupérer un nombre spécifique de balles et avancer pour combattre un autre nombre spécifique de dragons, survivra-t-il ?

Renvoie vrai si oui, faux sinon :)

### Objectif : Vérifier si le nombre de balles est suffisant

```java

class Solution {
  public static boolean hero(int bullets, int dragons) {
    return bullets >= (long) dragons * 2;
  }

  public static void main(String[] args){
    System.out.println(hero(10,5));
  }
}
```

# Exercice 26 array sorts

## Méthode Arrays.sort(numbers) :

Arrays.sort(numbers) trie le tableau numbers dans l'ordre croissant. Cette méthode utilise un algorithme de tri optimisé (généralement Timsort) pour organiser les éléments du plus petit au plus grand. Après l'appel, les éléments du tableau sont réarrangés directement dans cet ordre.

## Conditions :

Créez une fonction qui **renvoie la somme des deux nombres positifs les plus bas** à partir d'un tableau d' **au moins 4 entiers positifs**. Aucun nombre flottant ou entier non positif ne sera transmis.

Pour Java, ces entiers seront en double précision (long).

Par exemple, lorsqu'un tableau est passé comme
`[19, 5, 42, 2, 77], la sortie doit être 7.`

`[10, 343445353, 3453445, 3453545353453]devrait revenir 3453455.`

### Traduction de l'Énoncé en Code

Trouver les deux plus petits nombres dans un tableau donné.
Additionner ces deux nombres et retourner le résultat.

#### Étapes pour résoudre le problème :

- Trier le tableau.
  Sélectionner les deux premiers éléments après le tri (les deux plus petits).

- dditionner ces deux éléments.
- Contraintes :

  - Le tableau contient toujours au moins 4 nombres positifs.
    Les nombres sont des long, donc capables de gérer des valeurs très grandes.

### Code :

```java
class Kata {
  public static long sumTwoSmallestNumbers(long[] numbers) {
    // Trier le tableau pour trouver les deux plus petits nombres
    Arrays.sort(numbers);
    // Additionner les deux premiers nombres après le tri
    return numbers[0] + numbers[1];
  }

  public static void main(String[] args) {
    // Exemples de test
    System.out.println(sumTwoSmallestNumbers(new long[]{19, 5, 42, 2, 77}));
    // Résultat attendu : 7

    System.out.println(sumTwoSmallestNumbers(new long[]{10, 343445353, 3453445, 3453545353453L}));
    // Résultat attendu : 3453455
  }
}
```

# Exercice 27

#### StringBuilder pour manipuler des chaînes dynamiques

StringBuilder est une classe en Java utilisée pour manipuler des chaînes de caractères de manière efficace. Contrairement à String, qui est immuable, StringBuilder permet des modifications directes **(ajout, suppression, etc.)** sans créer de nouveaux objets. Idéal pour manipuler des chaînes dynamiques.

### Différence entre StringBuilder et String

#### String :

- **Immuable :** Une fois créé, son contenu ne peut pas être modifié.
  Méthodes comme substring, indexOf, ou length permettent d'accéder à son contenu sans le modifier.

#### StringBuilder :

- **Modifiable (mutable) :** Son contenu peut être modifié directement.
  Méthodes spécifiques comme append, reverse, insert, et delete sont conçues pour manipuler les chaînes efficacement.

#### Consignes

Complétez la solution de manière à inverser la chaîne qui lui est transmise.

```
'world'  =>  'dlrow'
'word'   =>  'drow'
```

## CODE :

```java
public class Kata {

  public static String solution(String str) {

    return new StringBuilder(str).reverse().toString();
  }

}
```

# Exercice 28 chaine de lettre qui se répètent

#### CharAt

La méthode charAt() renvoie une nouvelle chaîne contenant le caractère (ou, plus précisément, le point de code UTF-16) à la position indiquée en argument.

```java
Exemple hors contexte

const sentence = 'The quick brown fox jumps over the lazy dog.';
const index = 4;
console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// Expected output: "The character at index 4 is q"
```

### Objectif :

Créer une chaîne où chaque lettre de l'entrée est répétée selon sa position (1 pour la première lettre, 2 pour la deuxième, etc.).
La première occurrence de chaque lettre est en majuscule, et le reste en minuscule.
Les parties sont séparées par des tirets (-).

### Approche :

- Parcourir la chaîne.
- Répéter chaque caractère selon sa position (1 pour le premier caractère, 2 pour le deuxième...).
- Appliquer les majuscules et les minuscules correctement.
- Joindre les parties avec des tirets.

## CODE :

```java
public class Accumul {

    public static String accum(String s) {
        // Création d'un StringBuilder pour construire le résultat final.
        // StringBuilder est utilisé pour manipuler les chaînes efficacement.
        StringBuilder result = new StringBuilder();

        // Parcours de chaque caractère de la chaîne d'entrée `s`.
        // On utilise une boucle `for` pour aller de l'indice 0 jusqu'à la fin de la chaîne.
        for (int i = 0; i < s.length(); i++) {
            // Extraction du caractère à l'indice actuel `i` et stockage dans la variable `c`.
            char c = s.charAt(i);

            // Conversion du caractère en majuscule pour le début de la séquence.
            result.append(Character.toUpperCase(c));

            // Ajout des répétitions en minuscule du caractère.
            // La boucle interne parcourt `j` de 0 jusqu'à `i` (exclu), ajoutant `i` répétitions.
            for (int j = 0; j < i; j++) {
                result.append(Character.toLowerCase(c));
            }

            // Ajout d'un tiret `-` après chaque séquence,
            // sauf pour la dernière lettre (quand `i` est le dernier indice).
            if (i < s.length() - 1) {
                result.append("-");
            }
        }

        // Conversion du StringBuilder en chaîne de caractères et retour du résultat final.
        return result.toString();
    }

    public static void main(String[] args) {
        // Tests pour vérifier que la fonction produit les résultats attendus.
        // Chaque entrée est transformée selon les règles du problème.
        System.out.println(accum("abcd"));     // Résultat attendu : "A-Bb-Ccc-Dddd"
        System.out.println(accum("RqaEzty"));  // Résultat attendu : "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
        System.out.println(accum("cwAt"));    // Résultat attendu : "C-Ww-Aaa-Tttt"
    }
}
```

### Décomposition du code :

Initialiser un StringBuilder pour **stocker le résultat** :

```java
StringBuilder result = new StringBuilder();
```

**Parcourir** la chaîne s **avec une boucle for** :

Utiliser l'indice pour accéder à chaque caractère et pour déterminer combien de fois il doit être répété.

```java
for (int i = 0; i < s.length(); i++) {
    // Obtenir le caractère à la position i
    char c = s.charAt(i);
}
```

Ajouter la lettre en majuscule :

```java
result.append(Character.toUpperCase(c));
```

Ajouter les répétitions en minuscule avec une boucle imbriquée :

```java
for (int j = 0; j < i; j++) {
    result.append(Character.toLowerCase(c));
}
```

Ajouter un tiret sauf après le dernier caractère :

```java
if (i < s.length() - 1) {
    result.append("-");
}
```

5. Assembler et Retourner
   Une fois toutes les parties construites, convertir le StringBuilder en une chaîne finale :

```java
return result.toString();
```

# Exercice 29

## Consignes :

## Split : retirer des elements d'une phrase :

```java
String[] words = s.split(" ");
Divise la chaîne d'entrée s en un tableau de mots,
en utilisant l’espace comme délimiteur.
```

## Consignes :

Écrivez une fonction qui calcule la moyenne des nombres dans un tableau donné.

Remarque : les tableaux vides doivent renvoyer 0.

```java
public class Kata {
    public static double find_average(int[] array) {
        // Vérifier si le tableau est vide
        if (array.length == 0) {
            return 0;
        }

        // Calculer la somme des éléments
        int sum = 0;
        for (int num : array) {
            sum += num;
        }

        // Retourner la moyenne
        return (double) sum / array.length;
    }

    public static void main(String[] args) {
        // Tests
        System.out.println(find_average(new int[]{1, 2, 3, 4})); // Résultat attendu : 2.5
        System.out.println(find_average(new int[]{10, 20, 30})); // Résultat attendu : 20.0
        System.out.println(find_average(new int[]{}));           // Résultat attendu : 0.0
    }
}
```

# Exercice 30 comparer les longueur min max horrible

## Consignes

Simplement, étant donné une chaîne de mots, renvoie la longueur du ou des mots les plus courts.

La chaîne ne sera jamais vide et vous n'avez pas besoin de tenir compte des différents types de données.

## CODE :

```java
public class Kata {
    public static int findShort(String s) {
        // Diviser la chaîne d'entrée s en un tableau de mots
        String[] words = s.split(" ");

        // Initialiser la longueur minimale avec la longueur du premier mot
        int minLength = words[0].length();


        // Cela signifie ; pour l'element words nous allons créer une occurence word sans le s qui va etre un string et va définir le type des sorties de ce for ?

        for (String word : words) {
            if (word.length() < minLength) {
                minLength = word.length();
            }
        }

        // Retourner la longueur minimale
        return minLength;
    }
}
```

# Exercice 30 comparer les longueur min max horrible

#### Tâche:

Étant donné un entier non négatif, 3par exemple, renvoyez une chaîne avec un murmure : "1 sheep...2 sheep...3 sheep...". L'entrée sera toujours valide, c'est-à-dire sans entier négatif.

## Append : pour rajouter des caractères à la suite

#### Ce que fait append :

```
append() ajoute du contenu (texte, nombres, caractères, etc.) à la fin d'un objet StringBuilder.
La chaîne est modifiée directement : Pas de création de nouveaux objets.
Chaînage possible : Vous pouvez enchaîner plusieurs appels de manière concise.
Performant : Plus rapide que l'opérateur + pour manipuler des chaînes longues ou répétitives.

```

```java
class Kata {
  public static String countingSheep(int num) {

    // Utiliser un StringBuilder
        StringBuilder resultByStringBuilder = new StringBuilder();

        // Boucler de 1 pour ajouter des moutontons
        for (int i = 1; i <= num; i++) {
          //Donc ici à chaque tour nous rajoutons le nombre i contenu dans le for
          //Pusi nosu y ajoutons un peu de texte avec append
            resultByStringBuilder.append(i).append(" sheep...");
        }

        // Retour de  la chaîne finale
        return resultByStringBuilder.toString();

  }
}
```

# Exercice 31 :

## Consignes

Écrivez une fonction qui prend un tableau de nombres et renvoie la somme des nombres. Les nombres peuvent être négatifs ou non entiers. Si le tableau ne contient aucun nombre, vous devez renvoyer 0.

```
Exemples
Entrée : [1, 5.2, 4, 0, -1]
Sortie :9.2

Entrée : []
Sortie :0

Entrée : [-2.398]
Sortie :-2.398
```

#### Hypothèses

Vous pouvez supposer que seuls des chiffres vous sont donnés.
Vous ne pouvez pas supposer la taille du tableau.
Vous pouvez supposer que vous obtenez un tableau et si le tableau est vide, renvoyez 0.
Les tests attendent une précision de 1e-4.

Ce que nous testons
Nous testons des boucles et des opérations mathématiques de base. Ceci est destiné aux débutants qui apprennent les boucles et les opérations mathématiques.
Les utilisateurs avancés peuvent trouver cela extrêmement simple et peuvent facilement écrire cela sur une seule ligne.

## CODE :

```java
public class SumArray {

  public static double sum(double[] numbers) {
    // On initialise la somme à zéro
    double somme = 0.0;

    // Puis nous allons parcourir le tableau passé en paramètre 'numbers'
    // avec une entité 'nombre' qui représente chaque élément du tableau
    // Pour chaque élément trouvé, on ajoute sa valeur à la somme de départ
    for (double nombre : numbers) {
      somme += nombre; // Ajout de l'élément courant à la somme
    }

    // Une fois que tous les éléments ont été parcourus et ajoutés,
    // on renvoie la somme totale calculée
    return somme;
  }

  public static void main(String[] args) {
    // Nous testons la méthode avec plusieurs tableaux de données

    // Exemple 1 : Tableau avec plusieurs nombres positifs et négatifs
    double[] tableau1 = {1, 5.2, 4, 0, -1};
    System.out.println(sum(tableau1)); // Résultat attendu : 9.2

    // Exemple 2 : Tableau vide
    // Cela vérifie si la méthode renvoie bien 0 lorsque le tableau est vide
    double[] tableau2 = {};
    System.out.println(sum(tableau2)); // Résultat attendu : 0

    // Exemple 3 : Tableau contenant un seul nombre négatif
    double[] tableau3 = {-2.398};
    System.out.println(sum(tableau3)); // Résultat attendu : -2.398

    // Les tests permettent de valider que la méthode fonctionne
    // correctement pour différents cas d'utilisation
  }
}
```

---

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
