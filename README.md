# Java






Study Guide v2.0
Abstraction
Abstraction
Abstraction is a process of hiding the implementation details and showing only functionality to the user.

Another way, it shows only essential things to the user and hides the internal details, for example, sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.

Abstraction lets you focus on what the object does instead of how it does it. 

Generalization
Generalization is the process of extracting shared characteristics from two or more classes, and combining them into a generalized superclass. Shared characteristics can be attributes, associations, or methods. 

Eg : The classes Piece of Luggage  and Piece of Cargo partially share the same attributes. From a domain perspective, the two classes are also very similar. During generalization, the shared characteristics  are combined and used to create a new superclass Freight . Piece of Luggage and Piece of Cargo become subclasses of the class Freight. Therefore the properties that are common to the classes Piece of Luggage and Piece of Cargo are placed in the superclass Freight - Identification, Weight and ID-Number are those properties. 


Specialization
Specialization means creating new subclasses from an existing class. If it turns out that certain attributes, associations, or methods only apply to some of the objects of the class, a subclass can be created. 

In the previous example for Generalization, we saw that the classes Piece of Luggage and Piece of Cargo shared similar properties that were placed in a superclass called Freight. When it comes to Specialization, if there is a property that is only applicable to a specific subclass, such as Degree of  Hazardousness, that property is placed in the class Piece of Cargo where-in this class also has all the properties of the Freight class with the concept of Generalization. 


Ways to achieve abstraction?
There are two ways to achieve abstraction in java

Abstract class (0 to 100%)
Interface (100%)
Abstract Class
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated. 

Some points to remember : 
An abstract class must be declared with an abstract keyword.
It can have abstract and non-abstract methods.
It cannot be instantiated.
It can have constructors and static methods also.
It can have final methods which will force the subclass not to change the body of the method.
Abstract Method
A method which is declared as abstract and does not have implementation is known as an abstract method. 

abstract void printStatus();  //no method body and abstract  
Example of Abstract Class with an Abstract Method
abstract class Bike{  // Abstract class 
  abstract void run();  // Abstract method
}  
class Honda4 extends Bike{  
void run(){System.out.println("running safely");}  
public static void main(String args[]){  
 Bike obj = new Honda4();  
 obj.run();  
}  
} 
Sample Exercise : 
To create an abstract class called Bank.
To create an abstract method called getRateOfInterest();
To create two subclasses called SBI - 7% and PNB - 5% as two banks that extend the abstract class Bank.
To implement different functionalities for the getRateOfInterest() method in the SBI and PNB classes through the concept of method overriding and print out the interest rate inside the main() method created separately in a test class called TestBank
@Revature
11730 Plaza America Drive, Reston, VA 20190




Study Guide v2.0
Interface
Interface?
An interface is a reference type in Java. It is similar to class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface.
Along with abstract methods, an interface may also contain constants, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.
Writing an interface is similar to writing a class. But a class describes the attributes and behaviors of an object. And an interface contains behaviors that a class implements.
Unless the class that implements the interface is abstract, all the methods of the interface need to be defined in the class.
Similarities between an interface and a class
An interface can contain any number of methods.
An interface is written in a file with a .java extension, with the name of the interface matching the name of the file.
The byte code of an interface appears in a .class file.
Interfaces appear in packages, and their corresponding bytecode file must be in a directory structure that matches the package name.
Differences between an interface and a class
You cannot instantiate an interface.
An interface does not contain any constructors.
All of the methods in an interface are abstract.
An interface cannot contain instance fields. The only fields that can appear in an interface must be declared both static and final.
An interface is not extended by a class, it is implemented by a class.
An interface can extend multiple interfaces.
Declaring Interfaces
The interface keyword is used to declare an interface. 

/* File name : NameOfInterface.java */
import java.lang.*;
// Any number of import statements

public interface NameOfInterface {
   // Any number of final, static fields
   // Any number of abstract method declarations\
}
An interface is implicitly abstract. You do not need to use the abstract keyword while declaring an interface.
Each method in an interface is also implicitly abstract, so the abstract keyword is not needed.
Methods in an interface are implicitly public.
Example
/* File name : Animal.java */
interface Animal {
   public void eat();
   public void travel();
}
Implementing Interfaces
When a class implements an interface, you can think of the class as signing a contract, agreeing to perform the specific behaviors of the interface. If a class does not perform all the behaviors of the interface, the class must declare itself as abstract.

A class uses the implements keyword to implement an interface. The implements keyword appears in the class declaration following the extends portion of the declaration.

Example
/* File name : MammalInt.java */
public class MammalInt implements Animal {

   public void eat() {
      System.out.println("Mammal eats");
   }

   public void travel() {
      System.out.println("Mammal travels");
   } 

   public int noOfLegs() {
      return 0;
   }

   public static void main(String args[]) {
      MammalInt m = new MammalInt();
      m.eat();
      m.travel();
   }
} 
Rules to Remember : 
A class can implement more than one interface at a time.
A class can extend only one class, but implement many interfaces.
An interface can extend another interface, in a similar way as a class can extend another class.
Extending Interfaces
An interface can extend another interface in the same way that a class can extend another class. The extends keyword is used to extend an interface, and the child interface inherits the methods of the parent interface. 

Example
// Filename: Sports.java
public interface Sports {
   public void setHomeTeam(String name);
   public void setVisitingTeam(String name);
}

// Filename: Football.java
public interface Football extends Sports {
   public void homeTeamScored(int points);
   public void visitingTeamScored(int points);
   public void endOfQuarter(int quarter);
}

// Filename: Hockey.java
public interface Hockey extends Sports {
   public void homeGoalScored();
   public void visitingGoalScored();
   public void endOfPeriod(int period);
   public void overtimePeriod(int ot);
}
The Hockey interface has four methods, but it inherits two from Sports. Thus, a class that implements Hockey needs to implement all six methods. Similarly, a class that implements Football needs to define the three methods from Football and the two methods from Sports. 

Extending Multiple Interfaces
A Java class can only extend one parent class. Multiple inheritance is not allowed. Interfaces are not classes, however, and an interface can extend more than one parent interface.

The extends keyword is used once, and the parent interfaces are declared in a comma-separated list.

Example
public interface Hockey extends Sports, Event
@Revature
11730 Plaza America Drive, Reston, VA 20190
