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

### Difference entre heritage association composition agrégation :

| **Critère**            | **Héritage**                                                                       | **Association**                                                            | **Composition**                                                                                     | **Agrégation**                                                                                              |
| ---------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Relation**           | Relation "est un" (is-a)                                                           | Relation "utilise/travaille avec"                                          | Relation "fait partie de"                                                                           | Relation "a un" (has-a), mais avec moins de dépendance.                                                     |
| **Dépendance**         | La classe enfant dépend de la classe parent et hérite de ses comportements.        | Les objets liés peuvent exister indépendamment.                            | L'objet "contenu" ne peut pas exister sans l'objet "contenant".                                     | Les objets liés peuvent exister indépendamment mais sont fortement associés pour une durée.                 |
| **Durée de vie**       | La classe parent et la classe enfant ont des cycles de vie liés par la hiérarchie. | Les objets ont des cycles de vie indépendants.                             | L'objet "contenu" est détruit si l'objet "contenant" est détruit.                                   | L’objet agrégé peut survivre indépendamment, mais une relation forte existe pendant leur association.       |
| **Représentation UML** | Représentée par une flèche simple pointant vers la classe parent.                  | Représentée par une ligne simple entre les deux classes.                   | Représentée par une ligne avec un losange rempli du côté du contenant.                              | Représentée par une ligne avec un losange vide du côté du contenant.                                        |
| **Exemple pratique**   | Une `Dog` est un `Animal` et hérite des attributs/méthodes d’`Animal`.             | Un `Dog` peut avoir un `Owner`, mais l'`Owner` peut exister sans le `Dog`. | Un `Animal` possède un `Heart`, et le `Heart` n’a pas de sens sans l’`Animal`.                      | Une `School` a plusieurs `Students`, mais les `Students` peuvent exister sans la `School`.                  |
| **Code typique**       | Utilisation du mot-clé `extends` pour définir une classe enfant.                   | L'objet "associé" est passé ou défini en paramètre.                        | L'objet "contenu" est créé dans le constructeur ou initialisé directement dans l'objet "contenant". | L'objet agrégé est passé au contenant dans le constructeur, mais n'est pas créé directement dans la classe. |

### Resumé des relations :

| **Relation** | **Clé de relation**       | **Exemple**                 |
| ------------ | ------------------------- | --------------------------- |
| Héritage     | "est un" (is-a)           | Un chien est un animal.     |
| Association  | "utilise/travaille avec"  | Un chien a un propriétaire. |
| Composition  | "fait partie de"          | Un animal a un cœur.        |
| Agrégation   | "a un", dépendance faible | Une école a des élèves.     |

![border](../assets/line/line-pink-point_r.png);

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
