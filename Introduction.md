## Introduction to Object Oriented Programming (OOPs)

- Classes and objects
- Method
- Construction
- static keyword
- this keyword


### Classes and Objects

**Class :** 
- represents a group of objects with similar behaviours
- class is just a blueprint which gives us a basic defition of something we want to model. (sancha)

**Object :** An entity that has state (represents the data) and behavior(represents the functionality) is known as an object. 


**Student Class :**


```java

public class Student {
	
	// Data members
	private String name;
	private int age;
	
	//Constructor
	public Student() {
		super();
	}
	public Student(String name) {
		super();
		this.name = name;
	}
	public Student(int age) {
		super();
		this.age = age;
	}
	public Student(String name, int age) {
		super();
		this.name = name;
		this.age = age;
	}
	
	// Member functions
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	
}

```


Main Class:
