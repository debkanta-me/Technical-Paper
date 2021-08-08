# OOPs: A way of Programming!
> Object Oriented Programming system is a way of programming that helps programmers to implement their real-world ideas, it enables them to think like they're working with real-world entities or objects.  
In the real world, things have the knowledge and can do various works. In OOPs, objects have the power to store knowledge/state/data/behaviors. [Read more](https://en.wikipedia.org/wiki/Object-oriented_programming)

> **Simula** is considered to be the first OOP language, but the popular ones are Java, Python, C#, C++, etc.
### **Basically, there are four most important components in OOPs:**  

* Abstraction
* Encapsulation
* Inheritance
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
        name = this.name;
        roll_no = this.roll_no;
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
        name = this.name;
        roll_no = this.roll_no;
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
