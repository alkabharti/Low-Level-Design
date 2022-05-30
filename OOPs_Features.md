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






