## Singleton Design Pattern :

Singleton Pattern says that just"define a class that has only one instance and provides a global point of access to it".

#### Properties
- Creational Design Pattern
- Only one instance of the class should exist
- Other classes should be able to get Instance of Singleton Class
- Used in Logging (only one person can login), Cache, Sessions, Drivers

#### Implementation
- Constructor should be private
- Public method for returning instance
- Instance type - private static

#### Initialisation Type
- Early Initialisation : creation of instance at load time.
- Lazy Initialisation : creation of instance when required.
- Thread safe Method Initialisation
- Thread safe block Initialisation



```java
/*
 * Singleton Design : Properties
 * a) Creational Design Pattern
 * b) Only one instance of the class should exist
 * c) Other classes should be able to get Instance of Singleton Class
 * d) Used in Logging (only one person can login), Cache, Sessions, Drivers
 * 
 */

class Singleton_Early {
	private static Singleton_Early instance = new Singleton_Early();
	private Singleton_Early() {
		
	}
	public static Singleton_Early getInstance() {
		return instance;
	}
}

class Singleton_Lazy {
	private static Singleton_Lazy instance;
	private Singleton_Lazy() {
		
	}
	public static Singleton_Lazy getInstance() {
		if(instance==null)
			instance = new Singleton_Lazy();
		return instance;
	}
}

class SingletonSynchronizedMethod {
	private static SingletonSynchronizedMethod instance;
	private SingletonSynchronizedMethod() {
		
	}
	public static synchronized SingletonSynchronizedMethod getInstance() {
		if(instance==null)
			instance = new SingletonSynchronizedMethod();
		return instance;
	}
}

class SingletonSynchronized {
	private static SingletonSynchronized instance;
	private SingletonSynchronized() {
		
	}
	public static SingletonSynchronized getInstance() {
		if(instance==null) {
			synchronized (SingletonSynchronized.class){
				if(instance==null)
					instance = new SingletonSynchronized();
			}
		}
		return instance;
	}
}

public class Singleton_Design_Pattern {

	public static void main(String[] args) {
		Singleton_Early s1 = Singleton_Early.getInstance();
		System.out.println(s1);
		Singleton_Early s2 = Singleton_Early.getInstance();
		System.out.println(s2);
		
		Singleton_Lazy s3 = Singleton_Lazy.getInstance();
		System.out.println(s3);
		Singleton_Lazy s4 = Singleton_Lazy.getInstance();
		System.out.println(s4);
		
		SingletonSynchronizedMethod s5 = SingletonSynchronizedMethod.getInstance();
		System.out.println(s5);
		SingletonSynchronizedMethod s6 = SingletonSynchronizedMethod.getInstance();
		System.out.println(s6);
		
		SingletonSynchronized s7 = SingletonSynchronized.getInstance();
		System.out.println(s7);
		SingletonSynchronized s8 = SingletonSynchronized.getInstance();
		System.out.println(s8);
		
	}
	/*
	 * Output :
	        Singleton_Early@726f3b58
		Singleton_Early@726f3b58
		
		Singleton_Lazy@ee7d9f1
		Singleton_Lazy@ee7d9f1
		
		SingletonSynchronizedMethod@1edf1c96
		SingletonSynchronizedMethod@1edf1c96
		
		SingletonSynchronized@6996db8
		SingletonSynchronized@6996db8
	 */
	
		

}

```

  
