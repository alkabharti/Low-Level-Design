## Prototype Design Pattern :

Prototype Pattern says that cloning of an existing object instead of creating new one and can also be customized as per the requirement.

This pattern should be followed, if the cost of creating a new object is expensive and resource intensive.

#### Properties :

- Creational Design Pattern
- Used when we want to avaoid multiple Object creation of same instance, instead we copy the object to new object and then we can modify as per the need. 

#### Implementation :

- Object which we are copying should provide copying feature by implementing Cloneable interface.
- We can override clone() method to implement as per our need. 


-----------------------------------------------------------------------------------------------------------------------------------------------------

### Example



```java
import java.util.*;

class Vehicle2 implements Cloneable {
	private List<String> VehicleList;

	public Vehicle2() {
		this.VehicleList = new ArrayList<String>();
	}

	public Vehicle2(List<String> list) {
		this.VehicleList = list;
	}

	public void insertData() {
		VehicleList.add("Honda amaze");
		VehicleList.add("Audi A4");
		VehicleList.add("Hyundai Creta");
		VehicleList.add("Maruti Baleno");
		VehicleList.add("Renault Duster");
	}

	public List<String> getVehicleList() {
		return this.VehicleList;
	}

	@Override
	public Object clone() throws CloneNotSupportedException {
		List<String> tempList = new ArrayList<String>();

		for (String s : this.getVehicleList()) {
			tempList.add(s);
		}

		return new Vehicle2(tempList);
	}
}

public class Prototype_Design_Pattern {

	public static void main(String[] args) throws CloneNotSupportedException {
		// TODO Auto-generated method stub
		Vehicle2 a = new Vehicle2();
		a.insertData();

		Vehicle2 b = (Vehicle2) a.clone();
		List<String> list = b.getVehicleList();
		list.add("Honda new Amaze");

		System.out.println(a.getVehicleList());
		System.out.println(list);

		b.getVehicleList().remove("Audi A4");
		System.out.println(list);
		System.out.println(a.getVehicleList());

	}
	/*
	 * Output :
	 * 	[Honda amaze, Audi A4, Hyundai Creta, Maruti Baleno, Renault Duster]
		[Honda amaze, Audi A4, Hyundai Creta, Maruti Baleno, Renault Duster, Honda new Amaze]
		[Honda amaze, Hyundai Creta, Maruti Baleno, Renault Duster, Honda new Amaze]
		[Honda amaze, Audi A4, Hyundai Creta, Maruti Baleno, Renault Duster]
	 * 
	 */
}

```
