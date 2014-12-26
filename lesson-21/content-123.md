# 題目三

(1) 該冰店另提供 C 套餐與 D 套餐兩類產品。C套餐可任點兩種原料，
    冰的份量加倍；D套餐可任點三種原料，冰的份量加倍。

(2) C 與 D 的冰加倍，所以成本一律增加2元，銷售的價格則為「原料總售價」的1.5倍。
    例如：C套餐選擇Apple及Mango，成本為6.0+2.0+2=10元
         售價為（10.0 + 5.0）*1.5 = 22.5元

(3) 某客人點了以下的產品，請取得下列三種冰加倍的產品，分別印出其cost(成本)、
    price(價格)及profit(利潤)。

    利潤 = 總收入 - 總成本
    
    C t1 = new C(new Apple(), new Banana());
    D t2 = new D(new Banana(), new Pudding(), new Strawberry());
    D t3 = new D(new Apple(), new Banana(), new Mango());

## 執行結果

```
t1 cost: 10.0
t1 price: 22.5
t1 profit: 12.5
t2 cost: 8.0
t2 price: 22.5
t2 profit: 14.5
t3 cost: 12.0
t3 price: 30.0
t3 profit: 18.0
```

## 程式碼

JPA06_3.java

```java
class JPA06_3 {
    public static void main(String args[]){
        C t1 = new C(new Apple(), new Banana());
        D t2 = new D(new Banana(), new Pudding(), new Strawberry());
        D t3 = new D(new Apple(), new Banana(), new Mango());
        System.out.println("t1 cost: " + t1.getCost());
        System.out.println("t1 price: " + t1.getPrice());
        System.out.println("t1 profit: " + t1.getProfit());
        System.out.println("t2 cost: " + t2.getCost());
        System.out.println("t2 price: " + t2.getPrice());
        System.out.println("t2 profit: " + t2.getProfit());
        System.out.println("t3 cost: " + t3.getCost());
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
...

class JPD06_1 {
    public static void main(String args[]){
        C t1 = new C(new Apple(), new Banana());
        D t2 = new D(new Banana(), new Pudding(), new Strawberry());
        D t3 = new D(new Apple(), new Banana(), new Mango());
        System.out.println("t1 cost: " + t1.getCost());
        System.out.println("t1 price: " + t1.getPrice());
        System.out.println("t1 profit: " + t1.getProfit());
        System.out.println("t2 cost: " + t2.getCost());
        System.out.println("t2 price: " + t2.getPrice());
        System.out.println("t2 profit: " + t2.getProfit());
        System.out.println("t3 cost: " + t3.getCost());
        System.out.println("t3 price: " + t3.getPrice());
        System.out.println("t3 profit: " + t3.getProfit());
    }
}
```
