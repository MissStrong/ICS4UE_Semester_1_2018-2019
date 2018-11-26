## Object-Oriented Programming

There are three programming methodologies: **sequential programming**, **procedural programming**, and **object-oriented programming**. 

* Sequential programming invovles executing a program line-by-line, in order.
* Procedural programming involves calling functions (i.e. methods, in Java) that perform routines and can be called at any point in a program.
* Object-oriented programming(OOP) is a programming methodology that involves separating a program into separate modules.

You have been using all three methodologies in this course. OOP has the highest potential among them all when creating complex programs. 


### Class Hierarchy

In order to use OOP to its highest potential, it is important to understand the different ways in which a class is associated with another class. There are three types of associations that classes can have: **aggregation**, **composition**, and **inheritance**.


### Aggregation
Aggregation can be referred to as a "has-a" association, and is a weak association. This occurs when an class (called the **superclass** or **parent class**) has a field that is an object belonging to another class (called the **subclass** or the **parent class**). For example, if you have a class called `CardGame` which represents a card game, you may have a field that represents a deck of cards, from a `Deck` class. In other words, a `CardGame` has-a `Deck`. 

Typically, in aggregation, the subclass can exist independly of the superclass. For example, once a card game is finished, the deck of cards still exists. Thus, when the `CardGame` object is destroyed, the `Deck` object isn't necessarily destroyed with it.


### Composition
Composition can be referred to as a "owns-a" association, and is a strong association. It is similar to aggregation, except the subclass typically cannot exist independely of the superclass.

Expanding on the previous example, the class called `CardGame` class may require an array of `CardGamePlayer` objects. Once the card game is done, there are no more players.  When the `CardGame` object is destroyed, the `CardGamePlayer` objects are mostly likely destroyed with it. (This isn't supposed to be morbid; it just means that the humans/computers who were playing the game are no longer labelled as "players".)

Whenever you're designing a program and are unsure whether two classes should use aggregation or composition, ask yourself whether one class "has" the other, or whether it "owns" the other.


### Inheritance
Inheritance can be referred to as a "is-a" association, and is a very strong association. Unlike aggregation and composition, the subclass inherits all the fields and methods from the superclass. 

There are two cases:
1. The superclass is an interface, and the subclass `implements` it.
2. The superclass is an class, and the subclass `extends` it.


### Implementing an Interface
Interfaces were briefly mentioned in the lesson *Abstract Data Types*. An interface is typically a category of classes. For example, `Queue` is an interface and the `PriorityQueue` class (among other types of queues) `implements` it. Objects cannot  be created from an interface, so there is no such thing as a plain `Queue` object.

An Interface contains methods with empty bodies, and no fields. When a subclass `implements` an interface, it must include the definitions of all the methods from the interface. You can use the keyword `@Override` to document this. Both method overloading (from the previous lesson) and method overriding are types of **polymorphism**: methods existing in many forms.

When you're creating an instance of a subclass, you can declare the type as the interface.

For example, these two lines accomplish essentially the same thing.
```java
Queue q = new PriorityQueue();
```

```java
PriorityQueue q = new PriorityQueue();
```


### Extending a Class
You've seen examples of the keyword `extends` this in your GUI assignments. In the `Change Exchange` assignment, the first line of the `Change` class is `public class Change extends javax.swing.JFrame {`. The `JFrame` class is what allows your program to display a GUI form using `JFrame` components.

Similarly to a method in a subclass of an interface, a method in a subclass of a class can be overridden, too. 

You can also leave the body of a method in the superclass empty by using the keyword `abstract` on the method and on the class. Abstract methods must be `public` and non-static.


### Abstract Classes
**Abstract classes** are classes that contain one or more `abstract` methods. A class that is not an abstract class is a **concrete class**.

Interfaces have a few things in common with abstract classes. Neither can be instantiated and both act as a template for its subclasses. However, there are also some key differences between them. 

* Interfaces have no fields. Abstract classes may have fields.
* All methods in an interface are abstract. Not all methods in an abstract class need to be abstract.
* A subclass can inherit multiple interfaces, but at most one class.

When deciding between an abstract class and an interface in your program, consider the differences above.
