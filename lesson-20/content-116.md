# 題目一

請為汽車零件設計一類別架構，以避免在不同的類別中重複的寫相同的程式碼： 

1. 請寫一個 Engine(引擊) 類別。1600cc引擎的成本是20000元, 2000cc引擎的成本是25000元。請製造一個1600CC的引擎及一個2000cc的引擎呼叫其getCost(成本)方法，印出其傳回值。
2. 請寫一個 Aircond(空調) 類別。Auto空調的成本是12000元，Manual空調的成本是10000元。請製造一個Auto的空調及一個Manual的空調，呼叫其getCost(成本)方法，印出其傳回值。
3. 請撰寫一個Sound(音響) 類別。一個音響的成本是2000，請製造一個Sound物件、呼叫其getCost方法，並將其傳回值印出。

![engine.png](/content/116/files/engine.png)

## 執行結果

```
1600 cost: 20000
2000 cost: 25000
Auto: 12000
Manual: 10000
Sound: 2000
```

## 程式碼

JPA06_1.java

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

public class JPA06_1 {
    public static void main(String args[]){
        Engine e1 = new Engine(1600);
        System.out.println("1600 cost: " + e1.getCost());
        Engine e2 = new Engine(2000);
        System.out.println("2000 cost: " + e2.getCost());
     
        Aircond a1 = new Aircond("auto");
        System.out.println("Auto: " + a1.getCost());
        Aircond a2 = new Aircond("manual");
        System.out.println("Manual: " + a2.getCost());
    
        Sound s1 = new Sound();
        System.out.println("Sound: " + s1.getCost());
    }
}
```

## 開始練習

```java
...

public class JPD06_1 {
    public static void main(String args[]){
        Engine e1 = new Engine(1600);
        System.out.println("1600 cost: " + e1.getCost());
        Engine e2 = new Engine(2000);
        System.out.println("2000 cost: " + e2.getCost());
     
        Aircond a1 = new Aircond("auto");
        System.out.println("Auto: " + a1.getCost());
        Aircond a2 = new Aircond("manual");
        System.out.println("Manual: " + a2.getCost());
    
        Sound s1 = new Sound();
        System.out.println("Sound: " + s1.getCost());
    }
}```
