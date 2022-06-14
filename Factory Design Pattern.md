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

-----------------------------------------------------------------------------------------------------------------------------------------------------

### Example


```java
abstract class Vehicle {
	public abstract int getWheel();

	public String toString() {
		return "Wheel: " + this.getWheel();
	}
}

class Car extends Vehicle {
	int wheel;

	Car(int wheel) {
		this.wheel = wheel;
	}

	@Override
	public int getWheel() {
		// TODO Auto-generated method stub
		return wheel;
	}

}

class Bike extends Vehicle {
	int wheel;

	Bike(int wheel) {
		this.wheel = wheel;
	}

	@Override
	public int getWheel() {
		// TODO Auto-generated method stub
		return wheel;
	}
}

class VehicleFactory {
	public static Vehicle getInstance(String type, int wheel) {
		if (type == "car")
			return new Car(wheel);
		else if (type == "bike")
			return new Bike(wheel);
		return null;
	}
}

public class Factory_Design_Pattern {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Vehicle car = VehicleFactory.getInstance("car", 4);
		System.out.println(car);

		Vehicle bike = VehicleFactory.getInstance("bike", 2);
		System.out.println(bike);

	}
}

```



