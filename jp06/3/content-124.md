# 題目四

(1) 請使用LinkedList另寫一個類別支援該店的外送服務。

(2) 外送服務可以計算一次外送服務的總售價、總成本及總利潤。

(3) 請各為以下兩次的外送，計算其總售價、總成本及總利潤。

    a. 外送1
       a-1：Apple, Banana
       a-2：Banana, Pudding, Strawberry
    b. 外送2
       b-1：Apple, Banana, Mango
       b-2：Apple, Banana
       b-3：Banana, Pudding, Strawberry
       b-4：Apple, Banana, Mango

## 執行結果

```
a Price: 30.0
a Cost: 14.0
a Profit: 16.0
b Price: 70.0
b Cost: 34.0
b Profit: 36.0
```

## 程式碼

JPA06_4.java

```java
import java.util.*;

class JPA06_4 {
    public static void main(String args[]){
        Deliver d1 = new Deliver();
        d1.addProduct(new A(new Apple(), new Banana()));
        d1.addProduct(new B(new Banana(), new Pudding(), new Strawberry()));
        System.out.println("a Price: " + d1.getTotalPrice());
        System.out.println("a Cost: " + d1.getTotalCost());
        System.out.println("a Profit: " + d1.getTotalProfit());
        Deliver d2 = new Deliver();
        d2.addProduct(new B(new Apple(), new Banana(), new Mango()));
        d2.addProduct(new A(new Apple(), new Banana()));
        d2.addProduct(new B(new Banana(), new Pudding(), new Strawberry()));
        d2.addProduct(new B(new Apple(), new Banana(), new Mango()));
        System.out.println("b Price: " + d2.getTotalPrice());
        System.out.println("b Cost: " + d2.getTotalCost());
        System.out.println("b Profit: " + d2.getTotalProfit());
    }
}

class Deliver {
    
    LinkedList<Product> v = new LinkedList<Product>();
    
    void addProduct(Product p){
        v.add(p);
    }
    
    double getTotalPrice(){
        double totalPrice = 0.0;
        for (Product p : v) {
            totalPrice += p.getPrice();
        }
        return totalPrice;
    }
    
    double getTotalCost(){
        double totalCost = 0.0;
        for (Product p : v) {
            totalCost += p.getCost();
        }
        return totalCost;
    }
    
    double getTotalProfit(){
        double totalProfit = 0.0;
        for (Product p : v) {
            totalProfit += (p.getPrice() - p.getCost());
        }
        return totalProfit;
    }
}

abstract class Product {
   
    abstract double getCost();
    
    abstract double getPrice();
    
    double getProfit(){
        return getPrice()-getCost();
    }
}

class A extends Product{
    Material m1, m2, m3;    
    A (Material in1, Material in2) {
        m1 = in1;
        m2 = in2;
    }
    double getCost(){
        return m1.getCost()+m2.getCost();
    }
    double getPrice(){
        return m1.getPrice()+m2.getPrice();
    }
}

class B extends Product{
    Material m1, m2, m3;    
    B (Material in1, Material in2, Material in3) {
        m1 = in1;
        m2 = in2;
        m3 = in3;
    }
    double getCost(){
        return m1.getCost()+m2.getCost()+m3.getCost();
    }
    double getPrice(){
        return m1.getPrice()+m2.getPrice()+m3.getPrice();
    }
}

class C extends A {
    
    C(Material m1, Material m2){
        super(m1, m2);
        //Material.addTotalCost(2);
    }
    double getCost(){
        return 2+super.getCost();
    }
    
    double getPrice(){
        return super.getPrice()*1.5;
    }
}

class D extends B {
    
    D(Material m1, Material m2, Material m3){
        super(m1, m2, m3);
        //Material.addTotalCost(2);
    }
    double getCost(){
        return 2+super.getCost();
    }
    
    double getPrice(){
        return super.getPrice()*1.5;
    }
}

abstract class Material{
    double cost;
    double price;

    Material(double c, double p){
        cost=c;
        price=p;
    }
    
    double getCost(){
        return cost;
    }
    
    double getPrice(){
        return price;
    }
}

class Banana extends Material{
    Banana(){
        super(2.0, 5.0);
    }
}

class Apple extends Material{
    Apple(){
        super(6.0, 10.0);
    }
}

class Pudding extends Material{
    Pudding(){
        super(3.0, 5.0);
    }
}

class Strawberry extends Material{
    Strawberry(){
        super(1.0, 5.0);
    }
}

class Mango extends Material{
    Mango(){
        super(2.0, 5.0);
    }
}
```

## 開始練習

```java
import java.util.*;

...

class JPD06_4 {
    public static void main(String args[]){
        Deliver d1 = new Deliver();
        d1.addProduct(new A(new Apple(), new Banana()));
        d1.addProduct(new B(new Banana(), new Pudding(), new Strawberry()));
        System.out.println("a Price: " + d1.getTotalPrice());
        System.out.println("a Cost: " + d1.getTotalCost());
        System.out.println("a Profit: " + d1.getTotalProfit());
        Deliver d2 = new Deliver();
        d2.addProduct(new B(new Apple(), new Banana(), new Mango()));
        d2.addProduct(new A(new Apple(), new Banana()));
        d2.addProduct(new B(new Banana(), new Pudding(), new Strawberry()));
        d2.addProduct(new B(new Apple(), new Banana(), new Mango()));
        System.out.println("b Price: " + d2.getTotalPrice());
        System.out.println("b Cost: " + d2.getTotalCost());
        System.out.println("b Profit: " + d2.getTotalProfit());
    }
}
```
