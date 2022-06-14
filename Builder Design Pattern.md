## Builder Design Pattern :

Builder Pattern says that "construct a complex object from simple objects using step-by-step approach"

#### Properties :

- Creational Design Pattern
- Used when we have too many arguments to send in COnstructor and it's hard to maintain the order.
- When we don't want to send all parameters in Object initialisation (Generally we send optional parameters as Null). 

#### Implementation :

- We create a **static nested class** which contains all arguments of other class. 
- As per naming convention, if class name is **Vehicle**, builder class should be **VehicleBuilder**
- Builder class have a public constructor with all required parameters.
- Builder class should have methods for optional parameters. Method will return the Builder object. 
- A **build()** method that will return the final Object.
- The main class Vehicle has private constructor so to create instance only via Builder class.
- The main class Vehicle has only getters.


-----------------------------------------------------------------------------------------------------------------------------------------------------

### Example



```java
class Vehicle1 {
	// required parameter
	private String engine;
	private int wheel;

	// optional parameter
	private int airbags;

	public String getEngine() {
		return this.engine;
	}

	public int getWheel() {
		return this.wheel;
	}

	public int getAirbags() {
		return this.airbags;
	}

	private Vehicle1(VehicleBuilder builder) {
		this.engine = builder.engine;
		this.wheel = builder.wheel;
		this.airbags = builder.airbags;
	}

	public static class VehicleBuilder {
		private String engine;
		private int wheel;

		private int airbags;

		public VehicleBuilder(String engine, int wheel) {
			this.engine = engine;
			this.wheel = wheel;
		}

		public VehicleBuilder setAirbags(int airbags) {
			this.airbags = airbags;
			return this;
		}

		public Vehicle1 build() {
			return new Vehicle1(this);
		}
	}
}

public class Builder_Design_Pattern {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Vehicle1 car = new Vehicle1.VehicleBuilder("1500cc", 4).setAirbags(4).build();
		Vehicle1 bike = new Vehicle1.VehicleBuilder("250cc", 2).build();

		System.out.print(car.getEngine() + " ");
		System.out.print(car.getWheel() + " ");
		System.out.println(car.getAirbags() + " ");

		System.out.print(bike.getEngine() + " ");
		System.out.print(bike.getWheel() + " ");
		System.out.print(bike.getAirbags() + " ");

	}
	/*
	 * Output :
	 	1500cc 4 4 
		250cc 2 0 
	 */

}

```




