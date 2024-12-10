 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# HERITAGE

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Definiton](#definition-)
- [Cas Pratique](#cas-pratique-)

  - [Creation de la classe parent animal](#creation-dune-classe-parent)
  - [Creation de la classe enfant dog](#creation-dune-classe-enfant-)
  - [Modification de la methode main](#modification-de-la-methode-main)

  - [Polymorphisme](#le-polymorphisme)
    - [Utiliser les super](#utiliser-les-super)
    - [Override](#override)
    - [Ajouter une autre classe enfant cat](#ajouter-une-autre-classe-enfant-cat)
  - [Abstraction & erreurs](#abstraction--erreurs)
    - [Intégration des Classes Abstraites :](#intégration-des-classes-abstraites-)
    - [Intégration des Interfaces :](#intégration-des-interfaces)
    - [Creation d'une interface Playable](#creation-dune-interface-playable)
    - [Dog implement la classe abstraite Playable:](#dog-implement-la-classe-abstraite-playable)
    - [Cat implement la classe abstraite Playable :](#cat-implement-la-classe-abstraite-playable-)

![border](../assets/line/border_deco_rb.png)

## Definition :

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

#### Tips Imagé

- Nosu pourrions utilsier un super avec une classe croissant de base qui aurait un certain cout ;
- Le but etant de ne pas se repeter **DRY** `Dont repeat yourself`
- en supposant que nous avons un croissant avec des pepites de chocolart nosu allosn passer par un super pour récupérer le calcul du prix de base pour lui ajouter les pepites de chocolat

#### 1/ Ajout d'un constructeur à Animal

- Dans un premier temps nous allons ajouter un constructeur pour la classe **Animal (le parent)** et nosu allons utiliser **Super dans dog**

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

---

### Pourquoi utiliser super ?

##### Approche 1 : Modifier l'attribut name directement après avoir créé l'objet

```java
Dog myDog = new Dog();
myDog.name = "Rex";
```

##### Approche 2 : Passer name en paramètre au constructeur

```java
Dog myDog = new Dog("Rex");
```

### Différence clé : Gestion de l’initialisation

##### Avec affectation directe (myDog.name = "Rex")

- L’attribut est modifiable à tout moment.
- L’objet est créé sans valeur pour name et reste dans un état partiellement initialisé jusqu’à ce que vous affectiez une valeur.

##### Avec un constructeur (new Dog("Rex"))

- L’attribut est initialisé dès la création de l’objet.
- L’objet est immédiatement complet et prêt à être utilisé.

---

# POLYMORPHISME

### Qu’est-ce que le polymorphisme ?

Le polymorphisme signifie "plusieurs formes". En Java, cela permet d’utiliser une méthode ou un objet de différentes manières selon le contexte.

- **Polymorphisme par redéfinition (Override) :** Une classe enfant peut redéfinir une méthode de la classe parent avec un comportement différent.
- **Polymorphisme par surcharge (Overloading) :** Une méthode dans une même classe peut être définie plusieurs fois avec des paramètres différents.

# Override

Explorons comment remplacer (override) une méthode et ajouter des méthodes spécifiques dans l’enfant.

## Tips visuel

- Si une classe Parent vehicule possède la methode **rouler** et que nous désirons utilsier un avion la méthode sera override pour permettre **voler**

### Ajouter un comportement personnalisé dans Dog

- Alors pour rajouter un override nous allons directement sur la **classe enfant** qui nécessite un ajustement

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

- Puis nous allons modifier **le main** pour voir les changements ( aucun changements à ce niveau on y va seulement pour lancer le **run** )

- Ainsi nous auront la sortie suivante :

```java
Rex is eating
Dog is eating noisily.
Rex is barking.
```

## Ajouter une autre classe Enfant CAT

- Nous allons ajouter une nouvelle classe CAT afin d'explorer les differences

- Dnas un premier temps nous allons ajouter un super comme pour l'exemple **de dog >>** afin de retrouver directement les parametres

```java
   Dog myDog = new Dog();
        myDog.name = "Rex";
        // est Héritée de la classe Parent
        ----------------------------
          Dog myDog = new Dog("Rex");

```

Excellente question ! Analysons en détail les deux approches pour comprendre ce qui se passe dans chacune :

- Puis dans le main nous allons ajouter la methode Cat ( attention les simple quotes ne focntionnent pas )

```java
 Cat myCat = new Cat("Whiskers");
        myCat.eat();
        myCat.meow();
```

- De cette facon :

```java
public class Main {
    public static void main(String[] args) {
        Dog myDog =  new Dog("Rex");
        // Ainsi nous pouvons utiliser directement dans l'enfant dog
        // Les METHODES HERITEES de ANIMAL
        // myDog.name = "Rex";
        // Parent
        myDog.eat();
        // Enfant
        myDog.bark();

        Cat myCat = new Cat("Whiskers");
        myCat.eat();
        myCat.meow();
    }
}
```

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
