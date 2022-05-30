## OOPs Features

- Inheritance
- Polymorphism
- Abstraction
- Encapsulation


------------------------------------------------------------------------------------------------------------------------------------------------------


Inheritance :

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


Plymorphism 


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




