## Singleton Design Pattern :

Singleton Pattern says that just"define a class that has only one instance and provides a global point of access to it".

#### Properties
- Creational Design Pattern
- Only one instance of the class should exist
- Other classes should be able to get Instance of Singleton Class
- Used in Logging (only one person can login), Cache, Sessions, Drivers

#### Implementation
- Constructor should be private
- Public method for returning instance
- Instance type - private static

#### Initialisation Type
- Early Initialisation : creation of instance at load time.
- Lazy Initialisation : creation of instance when required.
- Thread safe Method Initialisation
- Thread safe block Initialisation




  
