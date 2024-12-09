 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# HERITAGE

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Definiton](#definition-)
- [Cas Pratique](#cas-pratique-)

![border](../assets/line/border_deco_rb.png)

# Definition :

L'héritage en Java permet à une classe enfant (ou classe dérivée) de réutiliser les attributs et méthodes d'une classe parent (ou classe de base).

# Cas pratique :

## Creation d'une classe Parent

- Nosu allosn partir d'un projet JAVA vierge ; au même niveau que main nous allons créer une class **Animal**

- Puis nosu allons ajouter le code suivant dans Animal

```java
public class Animal{
    String name;

    void eat(){
        System.out.println(name + " is eating");
    }
}
```

## Creation d'une classe Enfant :

- Puis nous allons créer une classe enfant **Dog** au même niveau que le main et la classe Animal

- Et nous allons rajouter un **extends** afin de lier la classe chien à la classe **Animal**

```java
public class Dog extends Animal{
void bark(){
    System.out.println(name + "is Barking");
}
}
```

## Modification de la methode Main

- Puis nous allons modifier la classe **Main**
- Nous allons y ajouter un **objet dog** et utiliser les methodes héritées et ajoutées;

- Ainsi on se rend compte que nous pouvons utiliser **les methodes void** que nosu avons créé au dessus ; l'heritage nous permettant d'accéder à toutes les methodes qui sont liées par l'extends
  -Extends sur children visant la classe Parents

```java
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.name = "Rex"; // Héritée de la classe Parent
        myDog.eat();        // Héritée de la classe Parent
        myDog.bark();       // Spécifique à la classe Enfant
    }
}
```

#### Sortie :

```
Rex is eating
Rex is Barking
```

## Utiliser les Super

- Dans un premier temps nous allons ajouter un constructeur pour la classe **Animal (le parent)** et nosu allons utiliser **Super dans dog**

#### 1/ Ajout d'un constructeur à Animal

- Mais quelques erreurs apparaissent dans noter code à ce niveau ;
- 1 usage 1 inheritor related problem

```java
public class Animal{ // 1 usage 1 inheritor related problem
    String name;
    // Constructeur dan le quel nous allons prendre les attributs
    // afin de les "lister"

    public Animal(String name) { // !!!!! no usages 1 related problem
        this.name = name;
    }
    void eat(){
        System.out.println(name + " is eating");
    }
}
```

- Puis nous allons retourner dans la methode main mais nous constatons que Dog() signale un problème

```java
      Dog myDog =  new Dog();
```

- Ainsi nosu allons intégrer directement dans les paramètres

```java
public class Main {
    public static void main(String[] args) {
      Dog myDog =  new Dog("Rex");
    //Ainsi nous pouvons utiliser directement dans l'enfant dog
    // Les METHODES heritées de ANIMAL
    // myDog.name = "Rex";
    //Parent
myDog.eat();
//Enfant
myDog.bark();
    }
}
```

- Ainsi le code fonctionne correctement nous avons uilisé le constructeur ( à travers les chamsp de paramètres de la classe Dog que nous avons appellé ; en appelant name de this.name )

![border](../assets/line/line-pink-point_r.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
