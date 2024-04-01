# JAVA-POO


L'héritage et l'override de méthode sont deux concepts fondamentaux de la programmation orientée objet (POO) qui permettent la réutilisation du code et la mise en œuvre de la polymorphie. Voici une explication de ces concepts en Java :

1. **Héritage :**
   L'héritage est un mécanisme qui permet à une classe (appelée classe dérivée ou sous-classe) d'hériter des attributs et des méthodes d'une autre classe (appelée classe de base, classe parent ou superclasse). La classe dérivée peut ainsi utiliser les membres (attributs et méthodes) de sa classe parente. En Java, l'héritage est réalisé en utilisant le mot-clé `extends`.

   Exemple :
   ```java
   class Animal {
       void sound() {
           System.out.println("Some sound");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Woof");
       }
   }
   ```

2. **Override de méthode :**
   L'override de méthode permet à une classe dérivée de fournir une implémentation spécifique d'une méthode déjà définie dans sa classe parente. Cela signifie que la classe enfant fournit sa propre implémentation de la méthode, qui remplace celle de la classe parente. Pour réaliser l'override en Java, la méthode dans la classe enfant doit avoir la même signature (même nom, même nombre et même type de paramètres) que la méthode dans la classe parente, et elle doit être annotée avec `@Override` pour une meilleure lisibilité.

   Exemple :
   ```java
   class Animal {
       void sound() {
           System.out.println("Some sound");
       }
   }

   class Dog extends Animal {
       @Override
       void sound() {
           System.out.println("Bark");
       }
   }
   ```

Dans cet exemple, la classe `Dog` hérite de la classe `Animal` et remplace la méthode `sound()` avec son propre comportement en utilisant l'override de méthode. Lorsqu'un objet de type `Dog` appelle la méthode `sound()`, il exécutera la version définie dans la classe `Dog`, et non celle de la classe `Animal`.

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



La surcharge de méthode est un concept de la programmation orientée objet qui permet de définir plusieurs méthodes avec le même nom dans une classe, mais avec des signatures différentes. La signature d'une méthode comprend le nom de la méthode ainsi que le nombre, le type et l'ordre de ses paramètres. En Java, deux méthodes sont considérées comme surchargées si elles ont le même nom mais des signatures de paramètres différentes.

Voici un exemple de surcharge de méthode en Java :

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

Dans cet exemple, la classe `Calculator` définit deux méthodes `add` avec le même nom mais des signatures de paramètres différentes. La première méthode prend deux paramètres de type entier (`int`), tandis que la deuxième méthode prend deux paramètres de type double (`double`). Bien que ces méthodes aient le même nom, elles sont considérées comme deux méthodes distinctes en raison de leurs signatures de paramètres différentes.

Lorsqu'une méthode surchargée est appelée, Java détermine quelle méthode exécuter en fonction des types des arguments fournis lors de l'appel de la méthode. Par exemple :

```java
public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        int sum1 = calc.add(3, 4);          // Appelle la méthode add(int, int)
        double sum2 = calc.add(2.5, 3.5);    // Appelle la méthode add(double, double)
    }
}
```

Dans cet exemple, la méthode `add(int, int)` est appelée avec des arguments entiers, tandis que la méthode `add(double, double)` est appelée avec des arguments doubles. Cela illustre comment Java résout les appels de méthode lorsqu'il y a surcharge de méthode.
