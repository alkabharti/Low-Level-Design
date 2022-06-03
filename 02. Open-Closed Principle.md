## Open-Closed Principle :

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

