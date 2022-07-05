## Dependency Inversion Principle :

The principle states that we must use abstraction (abstract classes and interfaces) instead of concrete implementations.


#### ShoppingMall.class

```java
public class ShoppingMall {

    private BankCard bankCard;

    public ShoppingMall(BankCard bankCard) {
        this.bankCard = bankCard;
    }

    public void doPurchaseSomething(long amount){
        bankCard.doTransaction(amount);
    }

    public static void main(String[] args) {
       // DebitCard debitCard=new DebitCard();
       // CreditCard creditCard=new CreditCard();

        BankCard bankCard=new CreditCard();
        ShoppingMall shoppingMall=new ShoppingMall(bankCard);
        shoppingMall.doPurchaseSomething(5000);
    }
}
```


#### DebitCard Class :


```java
public class DebitCard implements BankCard{

    public void doTransaction(long amount){
        System.out.println("payment using Debit card");
    }
}
```

#### CreditCard Class :


```java
public class CreditCard implements BankCard{

    public void doTransaction(long amount){
        System.out.println("payment using Credit card");
    }
}
```

#### Interface BankCard :


```java
public interface BankCard {

    public void doTransaction(long amount);
}
```



