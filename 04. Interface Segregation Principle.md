## Interface Segregation Principle :
The principle states that the larger interfaces split into smaller ones. Because the implementation classes use only the methods that are required. We should not force the client to use the methods that they do not want to use.


```java
public interface UPIPayments {

    public void payMoney();

    public void getScratchCard();


}
```

```java
public interface CashBackManager {

    public void getCashBackAsCreditBalance();
}
```


```java
public class Paytm implements UPIPayments {

    public void payMoney() {

    }

    public void getScratchCard() {

    }

}
```


```java
public class GooglePay implements UPIPayments,CashBackManager {

    public void payMoney() {

    }

    public void getScratchCard() {

    }

    public void getCashBackAsCreditBalance() {
      //this features is there in gpay
    }
}
```


```java 
public class Phonepe implements UPIPayments {
    public void payMoney() {

    }

    public void getScratchCard() {

    }


}
```

