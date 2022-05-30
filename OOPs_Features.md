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


