## Unified Modelling Language

Unified Modelling Langauge (UML) is a popular standard for modelling relations in OOP. It is not specific to Java.

### Classes

Each class (or interface) is represented by a rectangular box divided into three sections. The top section contains the name of the class, the middle section contains the names of the fields and the bottom section contains the names and parameters of the methods.

If it is an interface, <<Interface>> is written directly above the interface name.

If it is an abstract class or an interface, it is written in italics (or cursive if it's drawn by hand).

To the left of each field and method is one of the following signs: +, -, and #. The + sign stands for `public`, - stands for `private`, and # stands for `protected` (or package-protected).

If a field or method is underlined, this indicates that it is `static`.

If a method is in italics, this indicates that it is an abstract method.

Here is an example.

// TODO

### Relations

Aggregation is denoted by a line that has a white/blank diamond on one end (the subclass) and an arrowhead on the other end (the superclass). Near the arrowhead, you can include how many the subclass objects are contained in the superclass, and what their names are. When writing how many of them there are, you can use ".." notation to denote a range (e.g. "1..5" means 1 to 5 inclusively and "2..*" means 2 or more).

Composition is denoted simialr as aggregation, except the diamond is entirely black.

Inheritance is denoted using a line with one arrow on one end (the superclass). The line can be accompanied with the word "extends" or "implements".

> Exercise 18.?
>
> This OldMaid program has several classes: OldMaidGame, Deck, Card, JokerCard, RegularCard, Player, HumanPlayer, and ComputerPlayer. Draw a UML diagram that shows the relationship amog all the classes.
