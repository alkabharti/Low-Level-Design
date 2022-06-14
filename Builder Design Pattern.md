Builder Design Pattern :

Builder Pattern says that "construct a complex object from simple objects using step-by-step approach"

Properties :

- Creational Design Pattern
- Used when we have too many arguments to send in COnstructor and it's hard to maintain the order.
- When we don't want to send all parameters in Object initialisation (Generally we send optional parameters as Null). 

Implementation :

- We create a static nested class which contains all arguments of other class. 
- As per naming convention, if class name is Vehicle, builder class should be VehicleBuilder
- Builder class have a public constructor with all required parameters.
- Builder class should have methods for optional parameters. Method will return the Builder object. 
- A build() method that will return the final Object.




