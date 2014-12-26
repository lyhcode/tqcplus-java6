# 題目一

請以避免在不同類別中重複寫相同的程式碼的方式，為某冰店設計其冰品的計價系統。

(1) 請為冰品的每個原料Apple(蘋果)、Banana(香蕉)、Pudding(布丁)、Strawberry(草莓)、Mango(芒果)設計類別及繼承的架構，並提供getCost, getPrice二個方法。

(2) 每種類原料的成本與售價如下表：

<table border="1">
    <tr bgcolor=#aaafff><td>class_name(類別名稱)</td><td>cost(成本)</td><td>price(售價)</td></tr>
    <tr><td>Apple</td><td>6.0</td><td>10.0</td></tr>
    <tr><td>Banana</td><td>2.0</td><td>5.0</td></tr>
    <tr><td>Pudding</td><td>3.0</td><td>5.0</td></tr>
    <tr><td>Strawberry</td><td>1.0</td><td>5.0</td></tr>
    <tr><td>Mango</td><td>2.0</td><td>5.0</td></tr>
</table>

(3) 請各產生一Apple, Banana, Pudding之物件，並印出它們的cost及 price。

## 執行結果

```
Apple cost: 6.0
Apple price: 10.0
Banana cost: 2.0
Banana price: 5.0
Pudding cost: 3.0
Pudding price: 5.0
```

## 程式碼

JPA06_1.java

```java
class JPA06_1 {
      
    public static void main(String args[]){
        Apple ap = new Apple();
        Banana ba = new Banana();
        Pudding pu = new Pudding();
        System.out.println("Apple cost: " + ap.getCost());
        System.out.println("Apple price: " + ap.getPrice());
        System.out.println("Banana cost: " + ba.getCost());
        System.out.println("Banana price: " + ba.getPrice());
        System.out.println("Pudding cost: " + pu.getCost());
        System.out.println("Pudding price: " + pu.getPrice());
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

class JPA06_1 {
      
    public static void main(String args[]){
        Apple ap = new Apple();
        Banana ba = new Banana();
        Pudding pu = new Pudding();
        System.out.println(ap.getCost());
        System.out.println(ap.getPrice());
        System.out.println(ba.getCost());
        System.out.println(ba.getPrice());
        System.out.println(pu.getCost());
        System.out.println(pu.getPrice());
    }
}
```
