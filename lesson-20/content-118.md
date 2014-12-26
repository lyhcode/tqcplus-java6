# 題目三

這家工廠決定增加一超級豪華型車款：

超級豪華型的成本 ＝ 豪華型的成本 ＋ 音響成本

這型車的售價也是成本的1.2倍。為這型車設計一個 SLuxCar 類別。

也請為這家工廠增加一個能夠比較兩部車子的售價何者較貴的方法。

顯示如Screen Dump 參考畫面。

## 執行結果

```
SLux cost: 49000.0
SLux price: 58800.0
Is SLuxCar more expensive than LuxCar? Yes!!
```

## 程式碼

JPA06_3.java

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
   	protected String expensive(Car ob) {
   		String ans = "No!";
   		if (this.price() > ob.price()) {
   		 	ans = "Yes!!";
   		}
   		return ans;   		
   	}
}

class BasicCar extends Car {
    public BasicCar(int c,String t) {
       	super(c,t);
    }
    protected double cost() {
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

class SLuxCar extends LuxCar {
	Sound s = new Sound();
	public SLuxCar(int c,String t) {
		super(c,t);
	}
    protected double cost() {
       return (super.cost() + s.getCost());
    }	
}

public class JPA06_3 {
    public static void main(String args[]) {
        SLuxCar slc = new SLuxCar(2000,"auto");
        System.out.println("SLux cost: "  + slc.cost());
        System.out.println("SLux price: " + slc.price());
        LuxCar lc = new LuxCar(2000,"auto");
        System.out.println("Is SLuxCar more expensive than LuxCar? " + slc.expensive(lc));
   }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String args[]) {
        SLuxCar llc = new SLuxCar(2000,"auto");
        System.out.println("SLux cost: "  + llc.cost());
        System.out.println("SLux price: " + llc.price());
        LuxCar lc = new LuxCar(2000,"auto");
        System.out.println("Is llc more expensive than lc? " + llc.expensive(lc));
   }
}
```
