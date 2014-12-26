# 題目二

(1) 該冰店提供 A 與 B 兩類套餐產品。

(2) A套餐可任點兩種原料，B套餐可任點三種原料。

(3) 某客人點了以下的產品，請getPrice（價格）方法取得price，利用getProfit（利潤）取得prifit，並印出以下三種產品的price及profit。

    利潤 ＝ 總收入 - 總成本。

    A t1 = new A(new Apple(), new Banana());
    B t2 = new B(new Banana(), new Pudding(), new Strawberry());
    B t3 = new B(new Apple(), new Banana(), new Mango());

## 執行結果

```
t1 price: 15.0
t1 profit: 7.0
t2 price: 15.0
t2 profit: 9.0
t3 price: 20.0
t3 profit: 10.0
```

## 程式碼

JPA06_2.java

```java
class JPA06_2 {
    public static void main(String args[]){
        A t1 = new A(new Apple(), new Banana());
        B t2 = new B(new Banana(), new Pudding(), new Strawberry());
        B t3 = new B(new Apple(), new Banana(), new Mango());
        System.out.println("t1 price: " + t1.getPrice());
        System.out.println("t1 profit: " + t1.getProfit());
        System.out.println("t2 price: " + t2.getPrice());
        System.out.println("t2 profit: " +t2.getProfit());
        System.out.println("t3 price: " + t3.getPrice());
        System.out.println("t3 profit: " + t3.getProfit());
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
...

class JPD06_2 {
    public static void main(String args[]){
        A t1 = new A(new Apple(), new Banana());
        B t2 = new B(new Banana(), new Pudding(), new Strawberry());
        B t3 = new B(new Apple(), new Banana(), new Mango());
        System.out.println("t1 price: " + t1.getPrice());
        System.out.println("t1 profit: " + t1.getProfit());
        System.out.println("t2 price: " + t2.getPrice());
        System.out.println("t2 profit: " +t2.getProfit());
        System.out.println("t3 price: " + t3.getPrice());
        System.out.println("t3 profit: " + t3.getProfit());
    }
}
```
