## Exercise 18-1

Create a class called Person using the following information:

A Person object can be created from the Person class.
A Person object contains three fields: a name (String), a gender (String), and an age (int).
A Person object can be instantiated by providing its name, gender, and age
See solution here.

public class Person {

    String name;
    String gender;
    int age;
    
    public Person (String name, String gender, int age) {
        this.name = name;
        this.gender = gender;
        this.age = age;
    }
}
