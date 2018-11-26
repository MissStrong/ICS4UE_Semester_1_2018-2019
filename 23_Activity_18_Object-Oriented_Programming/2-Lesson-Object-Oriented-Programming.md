## Object-Oriented Programming

There are three programming methodologie: **sequential programming**, **procedural programming**, and **object-oriented programming**. 

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
Composition can be referred to as a "owns-a" association, and is a strong association. It is similar to aggregation, except the subclasses typically cannot exist independely of the superclass.

Expanding on the previous example, the class called `CardGame` class may require an array of `CardGamePlayer` objects. Once the card game is done, there are no more players.  When the `CardGame` object is destroyed, the `CardGamePlayer` objects are mostly likely destroyed with it. (This isn't supposed to be morbid; it just means that the humans/computers who were playing the game are no longer labelled as "players".)

Whenever you're designing a program and are unsure whether two classes should use aggregation or composition, ask yourself whether one class "has" the other, or whether it "owns" the other.


### Inheritance
