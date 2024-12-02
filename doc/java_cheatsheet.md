 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# JAVA CHEAT SHEET

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Gestion des entrées et sorties](#1-gestion-des-entrées-et-sorties)
- [Opérateurs mathématiques](#2-opérateurs-mathématiques)
- [Manipulation des chaînes de caractères](#3-manipulation-des-chaînes-de-caractères)
- [Structures conditionnelles](#4-structures-conditionnelles)
- [Boucles](#5-boucles)
- [ Collections de données](#6-collections-de-données)
- [Gestion des erreurs](#7-gestion-des-erreurs)
- [Manipulation des fichiers](#8-manipulation-des-fichiers)
- [Programmation orientée objet (POO)](#9-programmation-orientée-objet-poo)
- [Concepts avancés](#10-concepts-avancés)

![border](../assets/line/border_deco_rb.png)

## **1. Gestion des entrées et sorties**

- **Scanner** : Utilisé pour lire les entrées utilisateur.

  ```java
  Scanner scanner = new Scanner(System.in);
  int nombre = scanner.nextInt(); // Lire un entier
  String texte = scanner.nextLine(); // Lire une chaîne
  double decimal = scanner.nextDouble(); // Lire un double
  scanner.close();
  ```

- **System.out.println()** : Affiche une ligne de texte dans la console.

  ```java
  System.out.println("Bonjour, Java!");
  ```

---

## **2. Opérateurs mathématiques**

- **Modulo (%)** : Retourne le reste d'une division entière.
  ```java
  int reste = 10 % 3; // reste = 1
  ```
- **Math** : Classe utilitaire pour les calculs mathématiques.
  - `Math.abs(-5)` : Valeur absolue (résultat : 5).
  - `Math.pow(2, 3)` : Puissance (résultat : 8).
  - `Math.sqrt(16)` : Racine carrée (résultat : 4).
  - `Math.max(5, 10)` : Maximum (résultat : 10).
  - `Math.min(5, 10)` : Minimum (résultat : 5).
  - `Math.random()` : Nombre aléatoire entre 0.0 et 1.0.

---

## **3. Manipulation des chaînes de caractères**

- **String** : Classe pour gérer les chaînes.
  - `String nom = "Java";`
  - `nom.length()` : Longueur de la chaîne.
  - `nom.toUpperCase()` : Convertit en majuscules.
  - `nom.toLowerCase()` : Convertit en minuscules.
  - `nom.contains("av")` : Vérifie si la chaîne contient un texte.
  - `nom.charAt(0)` : Retourne le caractère à l’index donné.
  - `nom.substring(1, 3)` : Extrait une sous-chaîne.
  - `nom.equals("JAVA")` : Compare deux chaînes (sensible à la casse).

---

## **4. Structures conditionnelles**

- **if/else** : Permet d’exécuter du code selon une condition.
  ```java
  if (x > 0) {
      System.out.println("x est positif");
  } else {
      System.out.println("x est négatif ou nul");
  }
  ```
- **switch** : Utilisé pour plusieurs cas.
  ```java
  switch (jour) {
      case 1: System.out.println("Lundi"); break;
      case 2: System.out.println("Mardi"); break;
        default: System.out.println("Autre jour");
  }
  ```

---

## **5. Boucles**

- **for** : Boucle à itérations fixes.
  ```java
  for (int i = 0; i < 5; i++) {
      System.out.println(i);
  }
  ```
- **while** : Boucle conditionnelle.
  ```java
  int i = 0;
  while (i < 5) {
      System.out.println(i);
      i++;
  }
  ```
- **do-while** : Boucle exécutée au moins une fois.
  ```java
  int i = 0;
  do {
      System.out.println(i);
      i++;
  } while (i < 5);
  ```

---

## **6. Collections de données**

- **Tableaux** : Structure de données fixe.
  ```java
  int[] nombres = {1, 2, 3};
  System.out.println(nombres[0]); // Affiche 1
  ```
- **ArrayList** : Liste dynamique.
  ```java
  ArrayList<String> liste = new ArrayList<>();
  liste.add("Java");
  liste.add("Python");
  liste.remove("Python");
  System.out.println(liste.get(0)); // Affiche Java
  ```

---

## **7. Gestion des erreurs**

- **try/catch** : Pour gérer les exceptions.
  ```java
  try {
      int resultat = 10 / 0; // Division par zéro
  } catch (ArithmeticException e) {
      System.out.println("Erreur : Division par zéro !");
  }
  ```

---

## **8. Manipulation des fichiers**

- **Lire un fichier** :
  ```java
  try {
      File fichier = new File("fichier.txt");
      Scanner scanner = new Scanner(fichier);
      while (scanner.hasNextLine()) {
          String ligne = scanner.nextLine();
          System.out.println(ligne);
      }
      scanner.close();
  } catch (FileNotFoundException e) {
      System.out.println("Fichier introuvable !");
  }
  ```
- **Écrire dans un fichier** :
  ```java
  try {
      FileWriter writer = new FileWriter("fichier.txt");
      writer.write("Bonjour, Java !");
      writer.close();
  } catch (IOException e) {
      System.out.println("Erreur d'écriture !");
  }
  ```

---

## **9. Programmation orientée objet (POO)**

- **Classe et objet** :

  ```java
  class Personne {
      String nom;

      // Constructeur
      Personne(String nom) {
          this.nom = nom;
      }

      // Méthode
      void saluer() {
          System.out.println("Bonjour, " + nom);
      }
  }

  public class Main {
      public static void main(String[] args) {
          Personne p = new Personne("Alice");
          p.saluer(); // Affiche : Bonjour, Alice
      }
  }
  ```

---

## **10. Concepts avancés**

- **Threads** : Pour la programmation parallèle.
  ```java
  Thread thread = new Thread(() -> {
      System.out.println("Thread en cours d'exécution");
  });
  thread.start();
  ```
- **Lambda** : Syntaxe pour les fonctions anonymes.
  ```java
  List<String> noms = Arrays.asList("Alice", "Bob");
  noms.forEach(nom -> System.out.println(nom));
  ```

---

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
