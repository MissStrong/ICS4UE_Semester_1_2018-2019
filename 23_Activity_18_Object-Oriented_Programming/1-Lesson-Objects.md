## Objects

An **object** is an instance (i.e. a concrete occurrence) of a class. For example, if you have the string `"Hello World!"` somewhere in your file, it would be a `String` object. 

In Java, all objects are instantiated using the class's **contructor method**. The constructor method has the same name as the class.

You've seen constructors used in GUI files. For example, in the *Change Exchange* assignent, the `Change` class has a public method called `Change()`. The body of this constructor method is `initComponents();`, which initializes all the components of the GUI.

To create an object belonging to a particular class, you often need to use the `new` keyword in conjunction with the constructor method. For example, to create an integer array list object, you can use `ArrayList<Integer> intArrayList = new ArrayList()`. 

Some classes have simpler ways of creating objects, without directly calling the constructor. For example, to create a `String` object, you don't need to do `String s = new String();`, you can instantiate and initialize it at the same time: `String s = "12345";`. Some classes have operations that call the constructor method for you. For example, to create an array of integers, you don't do `Array<Integer> intArray = new Array(5);` (this actually won't work), you would do `int[] intArray = int[5]` instead.

Since primitive data types don't belong to a class, you don't need to use the `new` keyword to create them.

The reason that you cannot create a `Math` object is that the constructor in the `Math` class is `private`. When you create your own classes, you can prevent a user from creating an object belonging to you class by making the class's constructor `private`. By default, every classe you create has a `public` constructor with a blank body. Every classes have a constructor regardless of whether it is explicietly written in the body of the class.


### Method Overloading

You can create methods with the same name within a class as long as at least one of these three criteria are met.
* They accept a different number of parameters.
* They accept different types of parameters. (Note: `int`, `long`, `short`, `byte`, `float`, `double` are all the same type: a numeric type). 
* They accept the same number of parameters, as long as the types are in a different order. (This is not recommended.)

For example, 
```java
public void example(int n) {
    System.out.println(n);
}

// This is fine.
public void example(int n, int m) {
    System.out.println(n + " " + m);
}

// This is fine.
public void example(String s) {
    System.out.println(s);
}

// This is not fine. NetBeans will put a red squiggly line.
public void example(double d) {
    System.out.prinln(d);
}

```

Even constructors can be overloaded. Here is an example.
```java
String name;

public Person() {
    name = "unknown";
}

public Person(String s) {
    name = s;
}
```

### Encapsulation

In order to directly access a field (variable or constant) in an object from outside its class, it has to be `public`. However, declaring a variable as `public` allows the user to modify its value. There are two ways to allow a user to access a field in an object from outside of the class, without allowing them to modify its value.

1. **Declare the variable as `final`.**     
This prevents the variable from being modified at all once it is initiated, making it a constant.   

The `Arrays` class uses this strategy: the `length` field is `final`, which is why you can access it using `arrayName.length`.

2. **Create a method that obtains the value of the variable**.    
You can declare the variable to be `private`, then create a `public` method that returns the value of the variable.  

The `ArrayList` classes uses this strategy: the `size` field is `private`, but `size()` is a `public` method that returns the size.

This concept of data hiding is called **encapsulation**. The "capsule" in this case is the class.
