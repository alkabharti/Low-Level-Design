## Factory Design Pattern :

A Factory Pattern or Factory Method Pattern says that just define an interface or abstract class for creating an object but let the subclasses decide which class to instantiate. In other words, subclasses are responsible to create the instance of the class.

The Factory Method Pattern is also known as Virtual Constructor.

#### Properties :

- Creational design Pattern
- Used when we have multiple sub-classes of a Super class and based on input we want to return one class instance. 
- It provides abstraction between implementation and client classes.
- Remove the instantiation of client classes from client code. 


#### Implementation :

- Super class can be interface or abstract class or basic class
- Factory class has a static method which returns the instance of sub class based on input.  
