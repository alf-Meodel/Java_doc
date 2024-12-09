 <a href="../README.md">
  <img src="../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_rt.png)

# BENCHMARK heritage association composition agrégation

![border](../assets/line/border_deco_rb.png)

### Benchmark entre heritage association composition agrégation :

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

![border](../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../assets/line/border_deco_l.png)
