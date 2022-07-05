## Decorator Design Pattern :

#### Properties :

- Structural Design Pattern
- Used when we want to modify functionality of an Object at runtime and it should not change individual Object functionality.
- e.g Adding different functionalities in Dress

![image](https://user-images.githubusercontent.com/23376002/177186357-d9c162ed-abc1-4d0d-8424-81b7ca014320.png)


### Example :

-------------------------------------------------------------------------------------------------------------


```java
interface Dress {
	public void assemble();
}

class BasicDress implements Dress {
	@Override
	public void assemble() {
		System.out.println("Basic Dress Features");
	}
}

class DressDecorator implements Dress {
	protected Dress dress;

	public DressDecorator(Dress c) {
		this.dress = c;
	}

	@Override
	public void assemble() {
		this.dress.assemble();
	}
}

class CasualDress extends DressDecorator {
	public CasualDress(Dress c) {
		super(c);
	}

	@Override
	public void assemble() {
		super.assemble();
		System.out.println("Adding Casual Dress Features");
	}
}

class SportyDress extends DressDecorator {
	public SportyDress(Dress c) {
		super(c);
	}

	@Override
	public void assemble() {
		super.assemble();
		System.out.println("Adding Sporty Dress Features");
	}
}

class FancyDress extends DressDecorator {
	public FancyDress(Dress c) {
		super(c);
	}

	@Override
	public void assemble() {
		super.assemble();
		System.out.println("Adding Fancy Dress Features");
	}
}

public class Decorator_Design_Pattern {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Dress sportyDress = new SportyDress(new BasicDress());
		sportyDress.assemble();
		System.out.println();

		Dress fancyDress = new FancyDress(new BasicDress());
		fancyDress.assemble();
		System.out.println();

		Dress casualDress = new CasualDress(new BasicDress());
		casualDress.assemble();
		System.out.println();

		Dress sportyFancyDress = new SportyDress(new FancyDress(new BasicDress()));
		sportyFancyDress.assemble();
		System.out.println();

		Dress casualFancyDress = new CasualDress(new FancyDress(new BasicDress()));
		casualFancyDress.assemble();
	}

}

```

### Output :

![image](https://user-images.githubusercontent.com/23376002/177187421-2a17e230-8050-4a8c-b55c-39eefac92874.png)






