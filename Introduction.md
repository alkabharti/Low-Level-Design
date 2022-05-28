## Introduction to Object Oriented Programming (OOPs)

- Classes and objects
- Method
- Constructor
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


```java

public class main {

	public static void main(String[] args) {
		
		/* 
		 * Instantiation : It means building an object from its class blueprint.
		 *                 For e.g. new Student() - creates an instance of Student
		 *                 
		 * new keyword : used to allocate memory at runtime.                
		 */
		
		/*
		 * Different ways to create an object
		 * 		1. Anonymous object - nameless
		 * 		2. Reference variable
		 */
		
		// 1. Anonymous object
		new Student();
		System.out.println(new Student().getName()); // null
		System.out.println(new Student().getAge()); // 0
		
		// 2. Reference variable
		Student s1 = new Student(); // Creating an object of class Student
		// The '=' operator assigns the instance of student to the variablle s1. 
		
		System.out.println(s1.getName()); // null
		System.out.println(s1.getAge()); // 0
		
		Student s2 = new Student("Alka", 24);
		
		System.out.println(s2.getName()); // Alka
		System.out.println(s2.getAge()); // 24
	}

}

```




