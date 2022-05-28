## Introduction to Object Oriented Programming (OOPs)

- Classes and objects
- Method
- Constructor
- static keyword
- this keyword


----------------------------------------------------------------------------------------------------------------------------------------------------


**Class :** 
- represents a group of objects with similar behaviours
- class is just a blueprint which gives us a basic defition of something we want to model. (sancha)


**Object :** An entity that has state (represents the data) and behavior(represents the functionality) is known as an object. 


**Method :** A method is a block of code or collection of statements or a set of code grouped together to perform a certain task or operation.

![image](https://user-images.githubusercontent.com/23376002/170814711-25def2a7-2545-49dd-b880-adeddf1865f6.png)

**Types of Methods :**

a) Predefined : that is already defined in the Java class libraries or build-in methods. e.g length(), equals() etc. 

b) User-defined : written by user
	- Static method : we can call it without creating an object e.g main class
	- Instance method : non-static,  it is necessary to create an object of its class. 
	
c) Abstract method : that does not have a body. 


**Constructor :**
- special type of method which is used to initialize the object.
- It is called when an instance of the class is created.
- At the time of calling constructor, memory for the object is allocated in the memory.

![image](https://user-images.githubusercontent.com/23376002/170815355-b8b6f420-1c51-4e14-8ad1-a58692443607.png)

![image](https://user-images.githubusercontent.com/23376002/170815388-67c52b0f-9994-49a4-a38d-9253ae4ed60b.png)



**Student Class :**


```java

public class Student {
	
	// Data members
	private String name;
	private int age;
	
	/*
	 * Constructor : 
	 * 	- same name as its class name
	 *  - no return type
	 *  - cannot be abstract, static, final
	 */
	
	// Default constructor
	public Student() {
		super();
	}
	
	// Parameterized constructor
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
	
	public Student(Student s) {
		super();
		this.name = s.name;
		this.age = s.age;
	}
	
	// Member functions
	/*
	 * Instance methods 
	 * 	a) Accessor or getters : reads value of variable
	 *  b) Mutator or setters : modify the value of variable
	 */
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

abstract class test {
	
	/*
	 * Abstract method : that does not have a body
	 * It can only be present in abstract class
	 */
	abstract void method();
}


```


**Main Class:**


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
		
		/*
		 * Copy constructor : copy the values from one object to another like
		 */
		
		Student s3 = new Student(s2);
		System.out.println(s3.getName()); // Alka
		System.out.println(s3.getAge()); // 24
		
	}

}

```


**static keyword :** used for memory management mainly.




