# OOPs: A way of Programming!

> Object Oriented Programming system is a way of programming that helps programmers to implement their real-world ideas, it enables them to think like they're working with real-world entities or objects.  
In the real world, things have the knowledge and can do various works. In OOPs, objects have the power to store knowledge/state/data/behaviors. [Read more](https://en.wikipedia.org/wiki/Object-oriented_programming)

> **Simula** is considered to be the first OOP language, but the popular ones are Java, Python, C#, C++, etc.
### **Basically, there are four most important components in OOPs:**  

* Encapsulation
* Inheritance
* Abstraction
* Polymorphism

![](https://facingissuesonitcom.files.wordpress.com/2019/09/oops-concept.jpg?w=1000)  

*We will separately understand them all later..*

### __But first there are few more fundamental terminologies that one needs to understand:__

> _**Class**_: It can be considered as a **blueprint** or **template** for creating objects.

In **Java** to create a class you need to use the __*class*__ keyword

Example of creating a class named "Student" with two fields name and roll_no:
```Java
public class Student {
    String name = "Debkanta Mitra"; //In  class these are called fields
    int roll_no = 21;
}
```
___
> _**Object**_: Basically, it's an instance of a class. Objects have two characteristics: They have states(fields) and behaviors(methods).

 A car is an object because it has states like color, model, engine, etc. as well as behaviors like speed, accelerator, music, etc.

An object is created from a class. We have already created the class named **Student**, so now we can use it to create objects.

To create an object of **Student**, specify the class name, followed by the object name, and use the keyword **new**:

```Java
public class Student {
    String name = "Debkanta Mitra";
    int roll_no = 21;

  public static void main(String[] args) {
    Student myObj = new Student(); // This is how we instantiate object from class
    System.out.println(myObj.name);
    System.out.println(myObj.roll_no);
  }
}

Output: 
Debkanta Mitra
21
```

__*A blueprint for a house design is like a class description. All the houses built from that blueprint are objects of that class.*__
___
> __*Method:*__ The Methods are similar to functions but in OOP they belong to the class and they're declared within a class and they perform a certain task. 

Now we will create a method in the __Student__ class named as __set_fields__, which will set all the fields of the class

```Java
public class Student {
    String name;
    int roll_no;

    public void set_fields(String name, int roll_no){ // this is how we can create different methods, that perform certain action
        this.name = name;
        this.roll_no = roll_no;
    }

  public static void main(String[] args) {
    Student Student1 = new Student();
    Student Student2 = new Student();

    Student1.set_fields("Debkanta Mitra", 21);
    Student2.set_fields("Sayan Mitra", 22);

    System.out.println(Student1.name+" "+Student1.roll_no);
    System.out.println(Student2.name+" "+Student2.roll_no);
  }
}

Output: 
Debkanta Mitra 21
Sayan Mitra 22
```
__*Now as you can see, you have the flexibility to set the fields for different objects using methods. Earlier you didn't have that flexibility without methods.*__
___
> __*Constructor:*__  Constructor can be considered as a **special** method with the same name as its class name, which has only one purpose! that is to **initialize** the fields of the object while instantiating it.

_*One thing to note here is constructors don't have any return type like methods do*_

```Java
public class Student {
    String name;
    int roll_no;

    Student(String name, int roll_no){ // here we're performing the same task using constructor, which we've previously done using method
        this.name = name;
        this.roll_no = roll_no;
    }

  public static void main(String[] args) {
    Student Student1 = new Student("Debkanta Mitra", 21); // here is how you can initialize the fields while instantiating the object using "Constructor"
    Student Student2 = new Student("Sayan Mitra", 22);

    System.out.println(Student1.name+" "+Student1.roll_no);
    System.out.println(Student2.name+" "+Student2.roll_no);
  }
}

Output: 
Debkanta Mitra 21
Sayan Mitra 22
```

## _Now, we're going to discuss the four main concepts that we had already mentioned in the beginning, you must understand to learn Object-Oriented Programming:_

> __*Encapsulation:*__ Encapsulation is a process of binding fields and methods together and also making sure that 'sensitive' data is hidden from users.

If you're creating a class, you're doing Encapsulation.  
Other ways to achieve Encapsulation:
* Declare class variables/attributes as private.
* Providing getter and setter methods to access and modify those variables.

Below is an example of Encapsulation:

```Java
public class Student {
  private String name; // private = restricted access

  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```
_**Note:**_ If we try to access the name attribute directly, it'll throw an error. As we try to access a __Private__ property.
___
> __*Inheritance:*__ Inheritance is a process where one class inherits all the property of another class. The class which inherits is called __"Child or Sub"__ class and the class being inherited from is called __" Parent or Super"__ class.

In java, to inherit from a class, we use the __extends__ keyword.

```Java
class Person {
  protected String name = "Debkanta Mitra"; //Person field
  public void speak() { // Person method
    System.out.println("Hello, world!");
  }
}

class Student extends Person { // here we're inheriting all the properties of Person class to Student class
  private int roll_no = 21; // Student field
  public static void main(String[] args) {

    // Create a Student object
    Student s1 = new Student();

    // Call the speak() method (from the Person class) on the s1 object
    s1.speak();

    // Display the value of the name attribute (from the Person class) and the value of the roll_no from the Student class
    System.out.println(s1.name + " " + s1.roll_no);
  }
}
```
__*Note:*__ Inheritance is useful for code **reusability**. You reuse the properties of an existing class by inheriting them.
___
> __*Abstraction:*__ Abstraction is the process of hiding unnecessary details and showing only the relevant information of an object to the user.

__, For example,__, when you log in to your bank account online, you enter your user_id and password and press login, what happens when you press login, how the input data is sent to the server, how it gets verified is all abstracted away from you.

In Java, Abstraction can be achieved with either abstract classes or interfaces. We will take an example using an abstract class.

```Java
abstract class Animal{  
  abstract void sound(); // without any method body and abstract keyword. Example of an abstract method.  
}  
class Dog extends Animal {  
  void sound(){
    System.out.println("woof!");
  }
}

class Pig extends Animal{
  void sound(){
    System.out.println("wee-wee!");
  }
}

public class Main{  
  public static void main(String args[]){  
    Dog obj = new Dog();  
    obj.sound();

    Pig obj1 = new Pig();
    obj1.sound();  
  }  
}

Output: 
woof!
wee-wee!
```
__*Note:*__ We can achieve 100% abstraction using interfaces. To learn about **interfaces** [read more](https://beginnersbook.com/2013/05/java-interface/)
___

> __*Polymorphism:*__ It means "many forms" and it allows us to perform a single action in different ways.

Polymorphism can be of two types: 
* Compile time polymorphism
* Runtime polymorphism 

First, we will take an example of compile time polymorphism

```Java
  public class AddNumber{

    public int add(int a, int b){
      return a + b;
    }

    public int add(int a, int b, int c){
      return a + b + c;
    }

    public static void main(String args[]){
      AddNumber obj = new AddNumber();

      System.out.println(obj.add(2, 3));
      System.out.println(obj.add(2, 3, 4));
    }
  }

  Output:
  5
  9
```

As we can see in the example above, we have a class **AddNumber** and inside it we've two methods with the same name **add**, but both are different by the number of arguments passed and both perform a single action in different ways.

To know what is runtime polymorphism pls [read here](https://beginnersbook.com/2014/01/method-overriding-in-java-with-example/)

Although we have covered almost all the OOPs concepts here, but these topics are broad and there is so much scope to learn these topics in detail with the help of examples. So [read more on OOPs](https://beginnersbook.com/2013/04/oops-concepts/)

>*__Below are all reference links that I have used__*
* [OOPs concepts: BeginnersBook](https://beginnersbook.com/2013/04/oops-concepts/)
* [Java OOP: w3schools](https://www.w3schools.com/java/java_oop.asp)
* [OOP: Everything you need to know about Object-Oriented Programming](https://medium.com/from-the-scratch/oop-everything-you-need-to-know-about-object-oriented-programming-aee3c18e281b)