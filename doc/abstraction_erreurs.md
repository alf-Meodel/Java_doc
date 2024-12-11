 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# Abstraction & Erreurs

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Introduction](#introduction)

## Mission

- [x] Découverte de l'Abstraction
  - [x] Bilan sur l'héritage
  - [x] Notion de classes abstraites
  - [x] Notion d'interface
- [x] Gestion des erreurs
  - [x] Utilisation des exceptions
  - [x] Mot clé finally
  - [x] Propagation des exceptions
  - [x] Création d'exceptions personnalisées
- [x] Initiation aux bonnes pratiques
  - [x] Découverte du principe SOLID
- [x] Exercices pratiques

![border](../assets/line/border_deco_rb.png)

# Introduction

# Abstraction & erreurs

### Intégration des Classes Abstraites :

- Nous allons transformer la classe **Animal** en classe abstraite pour la rendre plus générique et imposer de comportements communs à ses sous classes

- nous allons donc créer uen methode abstraite puis il ne faut pas oublier de **préciser** dans l'entête de noter classe que c'est une **methode abstraite**

```
abstract void makeSound();
```

- ainsi nous avons pour l'exemple suivant une methode abstraite et une methode contrète

### Animal en classe abstract

```java
public abstract class Animal{
    String name;
    // Constructeur dan le quel nous allons prendre les attributs
    // afin de les "lister"
    public Animal(String name) {
        this.name = name;
    }
    //Methode abstraite
    abstract void makeSound();
    //Methode concrète
    void eat(){
        System.out.println(name + " is eating");
    }
}
```

- Puis nous allons adapter le reste de notre code en fonction de notre **nouvelle abstraction** en utilisant activement **make sound**

### Cat qui utilise une methode astract de la classe Animal

```java
public class Cat extends Animal{
//Donc nous allons utiliser super
    public Cat(String name){
        super(name);
    }
//   void meow(){
//  System.out.println( name = " is meowing");
//}
@Override
    void makeSound(){
    System.out.println(name + "is meowing");
}
}
```

- Nous allons aussi rajouter la classe abstraite que nous avons rajouté dans notre **classe parente**

```
 @Override
    void makeSound() {
        System.out.println(name + " is barking.");
    }
```

- ce qui nosu donne :

### Dog qui utilise une methode astract de la classe Animal

```java
public class Dog extends Animal {
    public Dog(String name) {
        super(name); // Appelle le constructeur de Animal
    }

    // OVERRIDE sur eat car ici Dog va manger differemment
    // on récupère donc la methode du parent afin de CREER
    // Une VERSION CUSTOM
    // au sein de la classe ciblé ici DOG enfant de ANIMAL

    @Override
    void makeSound() {
        System.out.println(name + " is barking.");
    }

    @Override
    void eat() {
        // Appelle la méthode de Animal
        super.eat();
        System.out.println("Dog is eating noisily.");
    }

    void bark() {
        System.out.println(name + " is barking.");
    }
}
```

# Intégration des Interfaces

- Pour les comportements spécifiques, nous allons utiliser une interface.
- Par exemple, certains (pas tous) animaux peuvent être joueurs ou nageurs.

- Nous allons donc créer une Interface `Playable` de la manière suivante

## Creation d'une interface Playable

```java
public interface Playable {
void play();
}
```

- Dans un premier temps nous allons rajouter dans l'entête de notre classe **chien**
- Que nous **implémentons la classe abstraite** dans laquelle se trouve la methode **play**

```java
public class Dog extends Animal implements Playable {
```

- Puis allons utiliser la methode abstraite diretement dans le code sous la forme d'un **Override**

```java
 @Override
    public void play() {
        System.out.println(name + " is playing fetch.");
    }
```

- Voici à quoi ressemble le code complet :

## Dog implement la classe abstraite Playable:

```java
public class Dog extends Animal implements Playable{
    public Dog(String name) {
        super(name); // Appelle le constructeur de Animal
    }

    // OVERRIDE sur eat car ici Dog va manger differemment
    // on récupère donc la methode du parent afin de CREER
    // Une VERSION CUSTOM
    // au sein de la classe ciblé ici DOG enfant de ANIMAL

    @Override
    void makeSound() {
        System.out.println(name + " is barking.");
    }

    //void bark() {
    //  System.out.println(name + " is barking.");
    // }

    @Override
    void eat() {
        // Appelle la méthode de Animal
        super.eat();
        System.out.println("Dog is eating noisily.");
    }

    @Override
    public void play() {
        System.out.println(name + " is playing fetch.");
    }
}
```

## Cat implement la classe abstraite Playable :

```java
public class Cat extends Animal implements Playable{
    //Donc nous allons utiliser super
    public Cat(String name){
        super(name);
    }
//  void meow(){
//  System.out.println( name = " is meowing");
//  }
@Override
    void makeSound(){
    System.out.println(name + "is meowing");
}
@Override
    public void play(){
    System.out.println(name + " joue avec une pelotte de laine ");
}
}
```

## Owner : Exploiter Interfaces et Héritage pour Accéder à des Attributs Parent

###### Résumé du Cours

- **Interfaces :** Le paramètre de la méthode est de type Playable, ce qui montre que la méthode repose sur une interface pour définir un comportement abstrait (play()).
- **Héritage :** La méthode utilise un cast explicite pour accéder à l'attribut name défini dans la classe parente Animal, qui n'est pas directement accessible via l'interface Playable.
- **Interaction dynamique :** La méthode démontre comment combiner ces deux mécanismes pour permettre des interactions complexes entre des objets partageant un comportement commun (via une interface) mais ayant des caractéristiques spécifiques héritées d'une classe parente.

Ajoute la possibilité de jouer avec les animaux en utilisant **l'interface Playable.**

```java
public class Owner {
String name;

// Constructeur de Owner

    public Owner(String name){
       this.name = name;
    }

    public void feed (Animal animal){
        System.out.println(name + " is feeding" + animal.name);
    }

    public void playWith (Playable animal){
        System.out.println(name + " is playing with " + ((Animal) animal).name);
        animal.play();
    }
}
```

```
Cette partie indique que l'objet animal doit être traité comme un objet de type Animal,
même s'il peut être une instance d'une sous-classe comme Dog ou Cat.
```

### .name :

```
Une fois que l'objet est considéré comme un Animal,
tu peux accéder aux attributs ou méthodes qui appartiennent
à la classe Animal (dans ce cas, l'attribut name).
```

## Explications :

##### Fonctionnement de playWith en quelques étapes :

###### Paramètre de la méthode :

```java
public void playWith (Playable animal){
        System.out.println(name + " is playing with " + ((Animal) animal).name);
        animal.play();
    }
```

- La méthode prend un paramètre animal de type Playable.
- Cela signifie que n'importe quel objet qui implémente l'interface Playable peut être passé à cette méthode.

## Conversion explicite avec (Animal) :

**((Animal) animal) : On "convertit" (ou cast) l'objet animal en type Animal.**
Cela permet d'accéder à des propriétés ou méthodes de la classe Animal qui ne font pas partie de l'interface Playable.

##### Accès à name:

**Une fois que l'objet est considéré comme un Animal,** on peut accéder à l'attribut name de la classe Animal via ((Animal) animal).name.

##### Appel à animal.play():

La méthode play() est appelée directement sur le paramètre animal, car cette méthode est définie dans l'interface Playable.

```

```

![border](../assets/line/line-pink-point_r.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
