# JavaSE-21.Polymorphism

See the Udemy course: https://www.udemy.com/course/curso-certificacion-profesional-desarrollador-java-se-11

Polymorphism is a fundamental concept in object-oriented programming that allows objects of different types to be treated as objects of a common type. 

There are two types of polymorphism in Java: compile-time (or static) polymorphism and runtime (or dynamic) polymorphism.

Let me illustrate both with examples:

## 1. Compile-time Polymorphism (Method Overloading):
```java
public class Calculator {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers (method overloading)
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method to concatenate two strings
    public String add(String a, String b) {
        return a + b;
    }

    public static void main(String[] args) {
        Calculator calculator = new Calculator();

        System.out.println(calculator.add(5, 10));            // Calls the first add method
        System.out.println(calculator.add(5, 10, 15));        // Calls the second add method
        System.out.println(calculator.add("Hello, ", "World!"));  // Calls the third add method
    }
}
```

In this example, the add method is overloaded with different parameter lists. The compiler determines the appropriate method to call based on the number and types of arguments.

## 2. Runtime Polymorphism (Method Overriding):

```java
// Base class
class Animal {
    public void makeSound() {
        System.out.println("Some generic sound");
    }
}

// Derived class 1
class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Bark! Bark!");
    }
}

// Derived class 2
class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow!");
    }
}

public class AnimalTest {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();

        dog.makeSound();  // Calls Dog's makeSound method
        cat.makeSound();  // Calls Cat's makeSound method
    }
}
```

In this example, Dog and Cat are subclasses of the Animal class, and they override the makeSound method.

At runtime, the actual type of the object (Dog or Cat) determines which version of makeSound is called.

That's polymorphism in a nutshell in Java! It's a powerful concept that promotes flexibility and code reuse.
