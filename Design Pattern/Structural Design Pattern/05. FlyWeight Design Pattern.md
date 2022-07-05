## FlyWeight Design Pattern :

#### Properties :

- Structural Design Pattern
- Used when we need to create many Object of a Class. We use it to reduce creation of Object. 
- Intrinsic Properties : which are same for a Object
- Extrinsic Properties : which are different for a Object


#### Implementation :

- Interface : which contain method - Employee
- Object : Individual Class - Developer, Tester
- Intrinsic Property (Developer : Fix the issue, Tester : Test the issue)
- Extrinsic Property : Skills
- We use Factory to use return Object : EmployeeFactory
- Client : Client Class
- We will assign issues as per skills


### Example :

-------------------------------------------------------------------------------------------------------------------------------------------------------


```java
import java.util.HashMap;
import java.util.Random;

interface Employee {
	public void assignSkill(String skill);

	public void task();
}

class Developer implements Employee {

	private final String JOB;
	private String skill;

	public Developer() {
		JOB = "Fix the issue";
	}

	@Override
	public void assignSkill(String skill) {
		this.skill = skill;
	}

	@Override
	public void task() {
		System.out.println("Developer with skill: " + this.skill + " with Job: " + JOB);
	}

}

class Tester implements Employee {

	private final String JOB;

	private String skill;

	public Tester() {
		JOB = "Test the issue";
	}

	@Override
	public void assignSkill(String skill) {
		this.skill = skill;
	}

	@Override
	public void task() {
		System.out.println("Tester with Skill: " + this.skill + " with Job: " + JOB);
	}

}

class EmployeeFactory {
	private static HashMap<String, Employee> m = new HashMap<String, Employee>();

	public static Employee getEmployee(String type) {
		Employee p = null;
		if (m.get(type) != null) {
			p = m.get(type);
		} else {
			switch (type) {
			case "Developer":
				System.out.println("Developer Created");
				p = new Developer();
				break;
			case "Tester":
				System.out.println("Tester Created");
				p = new Tester();
				break;
			default:
				System.out.println("No Such Employee");
			}

			m.put(type, p);
		}
		return p;
	}
}

public class FlyWeight_Design_Pattern {

	private static String employeeType[] = { "Developer", "Tester" };
	private static String skills[] = { "Java", "C++", ".Net", "Python" };

	public static void main(String[] args) {
		for (int i = 0; i < 10; i++) {
			Employee e = EmployeeFactory.getEmployee(getRandEmployee());

			e.assignSkill(getRandSkill());

			e.task();
		}
	}

	public static String getRandEmployee() {
		Random r = new Random();
		int randInt = r.nextInt(employeeType.length);

		return employeeType[randInt];
	}

	public static String getRandSkill() {
		Random r = new Random();
		int randInt = r.nextInt(skills.length);

		return skills[randInt];
	}

}

```


### Output :

![image](https://user-images.githubusercontent.com/23376002/177202741-35b6b2e1-c3d3-46db-b6f5-703f797e56e6.png)





