## Solid Principles :

- S : Single Responsibility Principle (SRP)
- O : Open-Closed Principle (OCP)
- L : Liskov Substitution Principle (LSP)
- I : Interface Segregation Principle (ISP)
- D : Dependency Inversion Principle (DIP)


![image](https://user-images.githubusercontent.com/23376002/171677669-a6979ca6-6a9c-4932-b1df-2fe0cd62e858.png)


Single Responsibility Principle :
The single responsibility principle states that every Java class must perform a single functionality. Implementation of multiple functionalities in a single class mashup the code and if any modification is required may affect the whole class.



```java
public class BankService {

    public long deposit(long amount, String accountNo) {
        //deposit amount
        return 0;
    }

    public long withDraw(long amount, String accountNo) {
        //withdraw amount
        return 0;
    }

    public void getLoanInterestInfo(String loanType) {
        if (loanType.equals("homeLoan")) {
            //do some job
        }
        if (loanType.equals("personalLoan")) {
            //do some job
        }
        if (loanType.equals("car")) {
            //do some job
        }
    }
    
    public void sendOTP(String medium) {
        if (medium.equals("email")) {
            //write email related logic
            //use JavaMailSenderAPI
        }
        if(medium.equals("mobile")){
            //write logic using twillio API
        }
    }

    public void printPassbook() {
        //update transaction info in passbook
    }


}
```


```java
public class BankService {

    public long deposit(long amount, String accountNo) {
        //deposit amount
        return 0;
    }

    public long withDraw(long amount, String accountNo) {
        //withdraw amount
        return 0;
    }
    
}
```

```java
public class LoanService {

    public void getLoanInterestInfo(String loanType) {
        if (loanType.equals("homeLoan")) {
            //do some job
        }
        if (loanType.equals("personalLoan")) {
            //do some job
        }
        if (loanType.equals("car")) {
            //do some job
        }
    }
}
```

```java
public class NotificationService {
    public void sendOTP(String medium) {
        if (medium.equals("email")) {
            //write email related logic
            //use JavaMailSenderAPI
        }
        if(medium.equals("mobile")){
            //write logic using twillio API
        }
    }
}
```

```java
public class PrinterService {

    public void printPassbook() {
        //update transaction info in passbook
    }
}
```





