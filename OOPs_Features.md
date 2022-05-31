## OOPs Features

- Inheritance
- Polymorphism
- Abstraction
- Encapsulation


------------------------------------------------------------------------------------------------------------------------------------------------------


### Inheritance :

a) Single Inheritance

```java
class Animal {
	void sound() {
		System.out.println("Animal sound");
	}
}

class Dog extends Animal {
	void sound1() {
		System.out.println("Dog sound");
	}
}

public class Single_Inheritance {

	public static void main(String[] args) {
		Dog dog = new Dog();
		dog.sound1(); // Dog sound
		dog.sound(); // Animal sound
	}

}

```

b) Multilevel Inheritance

```java
class Home {
	void home() {
		System.out.println("Home");
	}
}

class Room extends Home {
	void room() {
		System.out.println("Room");
	}
}

class One_bhk extends Room {
	void display() {
		System.out.println("1 BHK");
	}
}

public class Multilevel_Inheritance {
	public static void main(String[] args) {
		One_bhk one = new One_bhk();
		one.display(); // 1 BHK
		one.room(); // Room
		one.home(); // Home
	}

}

```


c) Hierarchical Inheritance


```java
class Animal {
	void sound() {
		System.out.println("Animal sound");
	}
}

class Dog extends Animal {
	void sound1() {
		System.out.println("Dog sound");
	}
}

class Cat extends Animal {
	void sound2() {
		System.out.println("Cat sound");
	}
}

public class Single_Inheritance {

	public static void main(String[] args) {
		Dog dog = new Dog();
		dog.sound1(); // Dog sound
		dog.sound(); // Animal sound
		
		Cat cat = new Cat();
		cat.sound2(); // Cat sound
		cat.sound(); // Animal sound
	}

}

```


### Polymorphism 

Method Overloading : Compile time Polymorphism

```java
/*
 * Method Overloading: changing no. of arguments
 */
class Add {
	public int add(int a, int b) {
		return a+b;
	}
	public int add(int a, int b, int c) {
		return a+b+c;
	}
}

/*
 * Method Overloading: changing data type of arguments
 */
class Subtract {
	public int subtract(int a, int b) {
		return a-b;
	}
	public double subtract(double a, double b) {
		return a-b;
	}
}

public class Method_Overloading {

	public static void main(String[] args) {
		Add a1 = new Add();
		System.out.println(a1.add(2, 3)); // 5
		System.out.println(a1.add(3, 4, 7)); // 14
		
		Subtract s1 = new Subtract();
		System.out.println(s1.subtract(8, 3)); // 5
		System.out.println(s1.subtract(9.4, 5.0)); // 4.4
	}

}

```


Type Promotion : 

![image](https://user-images.githubusercontent.com/23376002/171024472-c65585c2-b0a1-4fce-a927-bc97470d8e56.png)


Method Overriding : (Run Time Polymorphism)
- If subclass (child class) has the same method as declared in the parent class.
- Consider a scenario where Bank is a class that provides functionality to get the rate of interest. However, the rate of interest varies according to banks. 

![image](https://user-images.githubusercontent.com/23376002/171093837-49f7bd40-3652-434c-aa94-a80f3ba95095.png)



Super Keyword : 
- super can be used to refer immediate parent class instance variable.
- super can be used to invoke immediate parent class method.
- super() can be used to invoke immediate parent class constructor.



```java

class Game {
	int players = 4;

	Game() {
		System.out.println("Game Constructor");
	}

	void display() {
		System.out.println("Playing Game");
	}
}

class Ludo extends Game {
	Ludo() {
		super(); // invoke parent class constructor
		System.out.println("Ludo Constructor");
	}

	void display() {
		System.out.println("Playing Ludo");
		System.out.println(super.players); // refer immediate parent class instance variable
		super.display(); // invoke parent class method
	}

}

public class Super_keyword {

	public static void main(String[] args) {
		Ludo l1 = new Ludo();
		l1.display();
		/*
		 * Output : Game Constructor 
		 * 	    Ludo Constructor 
                 * 	    Playing Ludo 
		 *	    4 
		 *          Playing Game
		 * 
		 */

	}

}

```

Final Keyword : used to restrict the user.

1) Java Final variable : If you make any variable as final, you cannot change the value of final variable(It will be constant).

```java
class Money {
	final int rupees = 100;

	void change() {
		rupees = 200;
	}
}

public class Final_keyword {
	public static void main(String[] args) {
		Money m = new Money();
		m.change();
	}
}

// Compilation Error

```


2) Java Final Method : If you make any method as final, you cannot override it.

```java
class Money {
	int rupees = 100;

	final void change() {
		rupees = 200;
		System.out.print(rupees);
	}
}

class Test extends Money {
	void change() {
		
	}
}
public class Final_keyword {
	public static void main(String[] args) {
		Money m = new Money();
		m.change();
	}
}

// Compilation Error
```

3) Java Final class : If you make any class as final, you cannot extend it.


```java
final class Money {
	int rupees = 100;

	final void change() {
		rupees = 200;
		System.out.print(rupees);
	}
}

class Test extends Money {
	void change() {
		
	}
}
public class Final_keyword {
	public static void main(String[] args) {
		Money m = new Money();
		m.change();
	}
}

// Compilation Error
```


Upcasting : 
If the reference variable of Parent class refers to the object of Child class. 

![image](https://user-images.githubusercontent.com/23376002/171108884-b3363d98-cab3-4faf-a054-87604972054a.png)


```java
class Bike {
	void run() {
		System.out.println("running");
	}
}

class Splendor extends Bike {
	void run() {
		System.out.println("running safely with 60km");
	}

	public static void main(String args[]) {
		Bike b = new Splendor();// upcasting
		b.run();
	}
}

//Output : running safely with 60km.
```

Note : A method is overridden, not the data members, so runtime polymorphism can't be achieved by data members.

```java
class Bike {
	int speedlimit = 90;
}

class Honda3 extends Bike {
	int speedlimit = 150;

	public static void main(String args[]) {
		Bike obj = new Honda3();
		System.out.println(obj.speedlimit);// 90
	}
}

```

