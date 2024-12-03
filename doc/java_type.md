 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# Les types en JAVA

![border](../assets/line/line-pink-point_l.png)

## Sommaire

- [Introduction](#introduction)
- [Les Types Principaux en Java](#les-types-principaux-en-java)
- [Les Types Référencés](#les-types-référencés-objets)
- [Différences Clés entre les Types Primitifs et Référencés](#différences-clés-entre-les-types-primitifs-et-référencés)

![border](../assets/line/border_deco_rb.png)

# Introduction

- **Types Primitifs** : Utilisés pour les données simples (nombres, caractères, booléens).
- **Types Référencés** : Fournissent plus de fonctionnalités et sont utilisés pour manipuler des objets complexes.

Ainsi nous utilisons les types primitifs pour optimiser les performances et les objets pour plus de flexibilité.

## ![border](../assets/line/line-pink-point_l.png)

# **Les Types Principaux en Java**

| **Type**      | **Taille**                 | **Valeur par Défaut** | **Plage de Valeurs**               | **Description et Usage**                                                                     |
| ------------- | -------------------------- | --------------------- | ---------------------------------- | -------------------------------------------------------------------------------------------- |
| **`byte`**    | 1 octet (8 bits)           | `0`                   | `-128` à `127`                     | Type numérique utilisé pour les petits nombres, notamment pour économiser de la mémoire.     |
| **`short`**   | 2 octets (16 bits)         | `0`                   | `-32,768` à `32,767`               | Plus grand que `byte`, mais plus petit que `int`. Utilisé dans des contextes spécifiques.    |
| **`int`**     | 4 octets (32 bits)         | `0`                   | `-2,147,483,648` à `2,147,483,647` | Type entier le plus utilisé pour les opérations numériques classiques.                       |
| **`long`**    | 8 octets (64 bits)         | `0L`                  | `-2^63` à `2^63-1`                 | Utilisé pour les grands nombres qui dépassent la capacité de `int`.                          |
| **`float`**   | 4 octets (32 bits)         | `0.0f`                | ≈ `±3.4*10^38`                     | Type à virgule flottante pour les calculs en précision simple (moins précis que `double`).   |
| **`double`**  | 8 octets (64 bits)         | `0.0d`                | ≈ `±1.7*10^308`                    | Type à virgule flottante en précision double, utilisé pour les calculs numériques complexes. |
| **`char`**    | 2 octets (16 bits)         | `'\u0000'`            | `'\u0000'` à `'\uffff'`            | Représente un seul caractère Unicode (lettres, chiffres, symboles).                          |
| **`boolean`** | 1 bit (variable selon JVM) | `false`               | `true` ou `false`                  | Utilisé pour représenter des valeurs logiques.                                               |

---

# **Les Types Référencés (Objets)**

| **Type**               | **Description**                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------- |
| **`String`**           | Chaîne de caractères (texte).                                                      |
| **`Integer`**          | Classe enveloppante pour `int`. Fournit des méthodes utilitaires pour les entiers. |
| **`Double`**           | Classe enveloppante pour `double`.                                                 |
| **`Boolean`**          | Classe enveloppante pour `boolean`.                                                |
| **`Array`**            | Structure pour stocker plusieurs valeurs du même type.                             |
| **`List`** (Interface) | Collection pour stocker des objets de manière ordonnée (ex. : `ArrayList`).        |
| **`Map`** (Interface)  | Collection clé-valeur (ex. : `HashMap`, `TreeMap`).                                |

---

# **Différences Clés entre les Types Primitifs et Référencés**

| **Aspect**              | **Types Primitifs**                            | **Types Référencés (Objets)**                              |
| ----------------------- | ---------------------------------------------- | ---------------------------------------------------------- |
| **Mémoire**             | Stockés dans la pile (stack), très légers.     | Stockés dans le tas (heap), nécessitent plus de mémoire.   |
| **Valeur ou Référence** | Contiennent directement les données (valeurs). | Contiennent une référence vers les données (objets).       |
| **Nullabilité**         | Ne peuvent pas être `null`.                    | Peuvent être `null`.                                       |
| **Fonctionnalités**     | Aucune méthode associée.                       | Fournissent des méthodes utilitaires (ex. : `toString()`). |
| **Performance**         | Plus rapides et moins gourmands en mémoire.    | Plus lourds mais plus flexibles.                           |

---

![border](../assets/line/line-pink-point_r.png)

<a href="#sommaire"> <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;"></a>

![border](../assets/line/border_deco_l.png)
