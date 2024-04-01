# JAVA-POO

En programmation orientée objet (POO) en Java, le polymorphisme est un concept clé qui permet à un objet d'être traité comme s'il était d'un type différent, mais en conservant son comportement spécifique à son type réel. Il existe deux types de polymorphisme en Java : le polymorphisme statique (lié à la surcharge de méthodes) et le polymorphisme dynamique (lié à l'héritage et à la redéfinition de méthodes).

1. **Polymorphisme statique (liaison tardive) :**
   - Cela se produit lorsqu'une méthode est surchargée dans une classe. La décision sur quelle méthode appeler est prise au moment de la compilation en fonction du type de référence.
   - Exemple :
     ```java
     class Animal {
         void sound() {
             System.out.println("Some sound");
         }
     }
     
     class Dog extends Animal {
         void sound() {
             System.out.println("Bark");
         }
     }
     
     public class Main {
         public static void main(String[] args) {
             Animal a = new Dog(); // Référence de type Animal, objet de type Dog
             a.sound(); // Appel de la méthode sound() de Dog
         }
     }
     ```

2. **Polymorphisme dynamique (liaison tardive) :**
   - Cela se produit lorsqu'une méthode est redéfinie dans une classe dérivée. La décision sur quelle méthode appeler est prise au moment de l'exécution en fonction du type réel de l'objet.
   - Exemple :
     ```java
     class Animal {
         void sound() {
             System.out.println("Some sound");
         }
     }
     
     class Dog extends Animal {
         void sound() {
             System.out.println("Bark");
         }
     }
     
     public class Main {
         public static void main(String[] args) {
             Animal a = new Dog(); // Référence de type Animal, objet de type Dog
             a.sound(); // Appel de la méthode sound() de Dog
         }
     }
     ```

Dans les deux cas, le polymorphisme permet à une classe de traiter des objets de différentes classes de manière uniforme, améliorant ainsi la flexibilité et la modularité du code.
