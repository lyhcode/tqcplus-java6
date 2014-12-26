# 題目四

(1) 請建立一個 Warehouse(倉庫) 類別，讀取 data.txt 內三台車子的資料，
     每一行即代表一台車，將此三台車放入此倉庫中。

(2) data.txt 內有三筆資料，分別是代表 B (Basic 基本款)、L (LuxCar 豪華
     型車款)、S (SLuxCar 超級豪華型車款) 的成本，超級豪華車款的成本需再加
     上音響成本，內容如下：
     
    B 1600 manual
    L 2000 auto
    S 2000 auto

(3) 一個倉庫物件內有一個 ArrayList 物件，這個 ArrayList 可以儲存車子。

(4) 請計算這個倉庫內，此三台車的總庫存成本及總售價 (成本的 1.2倍)，
     顯示如Screen Dump參考畫面。
     
(5) 若找不到data.txt 檔案，則顯示【File not found!】。

## 執行結果

```
Total cost: 131000.0
Total price: 157200.0
```

## 程式碼

JPA06_4.java

```java
import java.lang.*;
import java.util.*;
import java.io.*;

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
   	public Car(int cc, String type) {		
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
    public BasicCar(int c, String t) {
       	super(c, t);
    }
    protected double cost() {
        return (e.getCost() + a.getCost() + 5000);
   	}  	
}
class LuxCar extends Car {
    public LuxCar(int c,String t){
     	super(c,t);
    }
    protected double cost(){
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

class Wharehouse {
    List<Car> v = new ArrayList<Car>();
    protected void addCar(Car ob) {
        v.add(ob);
    }
    protected double TotalCost() {
        double tc = 0;
        for (Car aCar : v) {
            tc = tc + aCar.cost();
        }
        return tc;	
    }
   protected double TotalPirce() {
       double tp = 0;
       for (Car aCar : v) {
           tp = tp + aCar.price();
       }
       return tp;	
   }
}

public class JPA06_4 {
    public static void main(String args[]) {
        Scanner sc = null;
        try {
            sc = new Scanner(new File("data.txt"));
        } catch (FileNotFoundException e) {
            System.out.println ("File not found!");
            // Stop program if no file found
            System.exit (0);
        }
        
        Wharehouse wh = new Wharehouse();
        while (sc.hasNext()) {
            String model = sc.next();
            int cc = sc.nextInt();
            String trans = sc.next();
            switch (model.charAt(0)) {
                case 'B':
                    wh.addCar(new BasicCar(cc, trans));
                    break;
                case 'L':
                    wh.addCar(new LuxCar(cc, trans));
                    break;
                case 'S':
                    wh.addCar(new SLuxCar(cc, trans));
                    break;
                default:
                    System.out.println("Bad model.");
                    break;
            }
        }
        System.out.println("Total cost: " + wh.TotalCost());   
        System.out.println("Total price: " + wh.TotalPirce()); 
    }	
}
```

## 開始練習

```java
                                                            
...

public class JPD06_4 {
    public static void main(String args[]) {
        Scanner sc = null;
        try {
            sc = new Scanner(new File("data.txt"));
        } catch (FileNotFoundException e) {
            System.out.println ("File not found!");
            // Stop program if no file found
            System.exit (0);
        }
        
        Wharehouse wh = new Wharehouse();
        while (sc.hasNext()) {
            String model = sc.next();
            int cc = sc.nextInt();
            String trans = sc.next();
            switch (model.charAt(0)) {
                ...
            }
        }
        System.out.println("Total cost: " + wh.TotalCost());   
        System.out.println("Total price: " + wh.TotalPirce()); 
    }	
}
```
