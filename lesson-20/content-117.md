# 題目二

1. 這家汽車工廠生產 BasicCar（基本型）及 LuxCar（豪華車款）兩種汽車。
2. 基本型的成本是：1600cc引擎成本 ＋ Manual 空調成本  +  5000 元。
3. 豪華車款的成本是：2000cc引擎成本 ＋ Auto 空調成本 + 10000 元。
3. 這兩型的售價都是成本的1.2倍。
5. 分別計算兩款車子的 cost （成本）與 price（售價），顯示如執行結果參考畫面。

![car.png](/content/file/117/car.png "Optional title")

## 執行結果

```
Basic cost: 35000.0
Basic price: 42000.0
Lux cost: 47000.0
Lux price: 56400.0
```

## 程式碼

JPA06_2.java

```java
class Part {
    int cost = 0;
    int getCost() {
        return cost;
    }
}

class Engine extends Part {
    public Engine(int cc) {
        if (cc == 1600) {
     	    cost = 20000;
  	   	} else {
  	   	    cost = 25000;	
  	   	}
    }
}

class Aircond extends Part {
    public Aircond(String type) {
        if (type.equals("auto")) {
  	   	    cost = 12000;
        } else {
  	   	    cost = 10000;	
  	   	}
    }
}

class Sound extends Part {
    public Sound() {
        cost = 2000;
    }
}

abstract class Car {
   	Engine e;
   	Aircond a;
   	public Car(int cc,String type) {		
   		e = new Engine(cc);
   		a = new Aircond(type);	
   	}
   	protected abstract double cost();
   	protected double price() {
   		return (this.cost() * 1.2);
   	}
}

class BasicCar extends Car {
    public BasicCar(int c,String t) {
       	super(c,t);
    }
    protected double cost(){
        return (e.getCost() + a.getCost() + 5000);
  	}  	
}

class LuxCar extends Car {
    public LuxCar(int c,String t) {
       	super(c,t);
    }
    protected double cost() {
        return (e.getCost() + a.getCost() + 10000);
   	}  	
}

public class JPA06_2 {
    public static void main(String args[]){
        BasicCar bc = new BasicCar(1600,"manual");
        System.out.println("Basic cost: " + bc.cost());
        System.out.println("Basic price: " + bc.price());
    
        LuxCar lc = new LuxCar(2000,"auto");
        System.out.println("Lux cost: " + lc.cost());
        System.out.println("Lux price: " + lc.price());
    }
}
```

## 開始練習

```java
...

public class JPD06_2 {
    public static void main(String args[]){
        BasicCar bc = new BasicCar(1600,"manual");
        System.out.println("Basic cost: " + bc.cost());
        System.out.println("Basic price: " + bc.price());
    
        LuxCar lc = new LuxCar(2000,"auto");
        System.out.println("Lux cost: " + lc.cost());
        System.out.println("Lux price: " + lc.price());
    }
}
```
