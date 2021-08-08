# OOPs: A way of Programming!
> Object Oriented Programming system is a way of programing which helps programmers to implement their real world ideas, it enables them to think like they're working with real world entities or objects.  
In real world, things have knowledge and can do various works. In OOPs, objects have that power to store knowledge/state/data/behaviours. [Read more](https://en.wikipedia.org/wiki/Object-oriented_programming)

> **Simula** is considered to be the first OOP language, but the popular one's are Java, Python, C#, C++ etc.
### **Basically, there are four most important components in OOPs:**  

* Abstraction
* Encapsulation
* Inheritance
* Polymorphism

![](https://facingissuesonitcom.files.wordpress.com/2019/09/oops-concept.jpg?w=1000)  

*We will separately understand them all later..*

### __But first  there are two more basic terminologies that one needs to understand:__

> _**Class**_: It can be considered as a **blueprint** or **template** for creating objects.

In **Java** to create a class you need to use the __*class*__ keyword

Example of creating class named "Student" with two fields name and roll_no:
```Java
public class Student {
    String name = "Debkanta Mitra"; //In  class these are called fields
    int roll_no = 21;
}
```
> _**Object**_: Basically, it's an instance of class. Objects have two characteristics: They have states(fields) and behaviors(methods).

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

