# JAVA Doc

<!-- Main image  -->

![border](./assets/line/border_deco_rt.png)

# Sommaire

- [Introduction](#objectif-et-consignes)

# Navigation

- [Exercices CodeWars](./doc/exercices_codewars.md)
- [JAVA Tools](./doc/java_tools.md)

![border](./assets/line/line-pink-point_l.png)

# Structure d'un programme Java

**Un programme Java est constitué de :**

### Classes :

Ce sont les blocs principaux qui contiennent le code.

### Méthodes :

Ce sont des blocs de code à l'intérieur des classes, qui contiennent les instructions pour effectuer des tâches spécifiques.

### La méthode main :

Le point d'entrée de tout programme Java. C'est là que l'exécution commence.

# Exemple :

```
public class Exemple {
    public static void main(String[] args) {
        System.out.println("Bonjour, monde!");
    }
}
```

### Décomposition et comprehension :

#### public class Exemple :

Définit une classe nommée Exemple.
Tout le code du programme se trouve à l'intérieur de cette classe.

#### public static void main(String[] args) :

C'est la méthode principale où l'exécution du programme commence.
Les parties importantes :

- **public** : Signifie que la méthode est accessible partout.
- **static** : Permet d'exécuter la méthode sans avoir besoin de créer un objet.
- **void** : Indique que la méthode ne retourne rien.
- **String[] args** : Permet de passer des arguments à la méthode si nécessaire (par exemple, depuis la ligne de commande).

System.out.println("Bonjour, monde!"); :

Affiche "Bonjour, monde!" dans la console.

## Les classes
Une classe est une structure qui contient des données (attributs) et des méthodes. Elle agit comme un plan pour créer des objets.

```
public class Voiture {
    // Attributs (propriétés de la classe)
    String marque;
    int vitesse;

    // Méthode (action de la classe)
    public void demarrer() {
        System.out.println(marque + " démarre !");
    }
}
```

Décomposition :
Attributs :

String marque; : La voiture a une marque (par exemple, "Toyota").
int vitesse; : La voiture a une vitesse (par exemple, 120 km/h).
Méthode demarrer :

Définit un comportement de la classe (affiche un message lorsqu'une voiture démarre).

##  Les méthodes
Une méthode est un bloc de code qui réalise une tâche. Elle peut :

Prendre des paramètres (informations nécessaires pour effectuer la tâche).
Retourner un résultat.

```
 Les méthodes
Une méthode est un bloc de code qui réalise une tâche. Elle peut :

Prendre des paramètres (informations nécessaires pour effectuer la tâche).
Retourner un résultat.
```

Décomposition :
public :

La méthode est accessible depuis l'extérieur de la classe.
int :

Le type de valeur que la méthode retourne (dans ce cas, un entier).
additionner(int a, int b) :

int a et int b sont des paramètres passés à la méthode.
La méthode retourne la somme de a et b.

```

```

<a href="#sommaire">
<img src="assets/button/back_to_top.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](./assets/line/line-teal-point_l.png)

![border](./assets/line/border_deco_rt.png)
