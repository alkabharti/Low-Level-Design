## Solid Principles :

- S : Single Responsibility Principle (SRP)
- O : Open-Closed Principle (OCP)
- L : Liskov Substitution Principle (LSP)
- I : Interface Segregation Principle (ISP)
- D : Dependency Inversion Principle (DIP)


![image](https://user-images.githubusercontent.com/23376002/171677669-a6979ca6-6a9c-4932-b1df-2fe0cd62e858.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------


### Single Responsibility Principle :
The single responsibility principle states that every Java class must perform a single functionality. Implementation of multiple functionalities in a single class mashup the code and if any modification is required may affect the whole class.


**BankService Class : It contains all the functionalities**


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

After implementing SRP we have created multiple classes to handle different functionalities.

**BankService.java Class**

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

**LoanService.java Class**


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

**NotificationService.java Class**

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

**PrinterService.java Class**

```java
public class PrinterService {

    public void printPassbook() {
        //update transaction info in passbook
    }
}
```


### Open-Closed Principle :
The open-closed principle states that according to new requirements the module should be open for extension but closed for modification.


**Notificationservice Interface**

```java
public interface Notificationservice {

    public void sendOTP(String medium);

    public void sendTransactionReport(String medium);

}
```

**EmailNotificationService Class**

```java
public class EmailNotificationService implements Notificationservice {
    public void sendOTP(String medium) {
        //write logic to integrate with email api
    }

    public void sendTransactionReport(String medium) {
        //write logic to integrate with email api
    }
}

```

**MobileNotificationService Class**

```java
public class MobileNotificationService implements Notificationservice {
    public void sendOTP(String medium) {
        //write the logic to send otp to mobile
        //twillo api
    }

    public void sendTransactionReport(String medium) {
        //write the logic to send otp to mobile
        //twillo api
    }
}
```

**WhatsAppNotificationService Class**

```java
public class WhatsAppNotificationService implements Notificationservice {

    public void sendOTP(String medium) {
        //logic to integrate whatsapp api
    }

    public void sendTransactionReport(String medium) {
        //logic to integrate whatsapp api
    }
}
```


