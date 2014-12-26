# 題目五

1. 此筆訂單資料如下： 

        MiniNote 1台
        Note15   1台
        PC       1台
     
2. 利潤 ＝ 總收入 - 總成本（非零件總成本）

3. 如果此次累積利潤超過20000，則以 Exception 印出信息。 

## 執行結果

```
This order exceeds 20000: 24760.0
```

## 程式碼

JPA06_5.java

```java
import java.util.LinkedList;
import java.util.Scanner;

abstract class Part {
    int cost;
    int getCost() {
        return cost;
    }
}

class LCD extends Part {
    int inch;
    LCD (int inch) {
        this.inch = inch;
        if (inch == 10) {
            this.cost = 2000;
        } else if (inch == 15) {
            this.cost = 2500;
        } else if (inch == 17) {
            this.cost = 3000;
        }
    }    
    int inch(){
        return inch;
    }
}

class CPU extends Part {
    double speed;
    CPU (double speed) {
        this.speed=speed;
        if (speed == 1.66) {
            this.cost = 6000;
        } else if (speed == 2.2) {
            this.cost = 8000;
        } else if (speed == 2.4) {
            this.cost = 11000;
        }
    }
    double speed(){
        return speed;
    }
}

class HD extends Part{
    int size;
    HD(int size){
        this.size=size;
        if (size == 120) {
            this.cost = 2400;
        } else if (size == 160) {
            this.cost = 2800;
        } 
    }
    int size(){
        return size;
    }
}

abstract class AllPC{
	abstract double getPrice();
    abstract double getCost();
	boolean isExpensive(AllPC another){
	    if (getPrice()>another.getPrice()){
	        return true;
	    }else{
            return false;
        }
	}
}

abstract class Notebook extends AllPC{
    LCD lcd;
    CPU cpu;
    HD hd;
    double getCost(){
        return (lcd.getCost()+cpu.getCost()+hd.getCost())*1.4;
    }
    double getPrice(){
        return (lcd.getCost()+cpu.getCost()+hd.getCost())*2.0;
    }
}

class MiniNote extends Notebook{
    MiniNote(){
        lcd = new LCD(10);
        cpu = new CPU(1.66);
        hd = new HD(120);
    }
}

class Note15 extends Notebook{
    Note15(){
       lcd = new LCD(15);
       cpu = new CPU(2.2);
       hd = new HD(160);
    }
}

abstract class PCandMultiPC extends AllPC {
    CPU cpu;
    HD hd;
    int CPUno;
    int HDno;
    int getPartCost() {
        return (cpu.getCost() * CPUno + hd.getCost() * HDno);
    }
    abstract double getCost();
    double getPrice() {
        return this.getPartCost() * 1.8;
    }
}

class PC extends PCandMultiPC{
    PC(){
        cpu = new CPU(2.4);
        hd = new HD(160);
        CPUno=1;
        HDno=1;
    }
    double getCost () {
        return super.getPartCost() + 500;
    }
}

class MultiPC extends PCandMultiPC{
    MultiPC(int CPUno, int HDno) {
        cpu = new CPU(2.4);
        hd = new HD(160);
        this.CPUno=CPUno;
        this.HDno=HDno;
    }
    double getCost () {
        return super.getPartCost() * 1.2;
    }
}

class Order {
    double profit=0;
    LinkedList<AllPC> pcs = new LinkedList<AllPC>();
    
    void in(AllPC allpc) throws Exception {
        pcs.add(allpc);
        if (this.profit() > 20000) {
            throw(new Exception());
        }
    }
    
    double profit() {
        double prof = 0;
        for (AllPC apc: pcs) {
            prof = prof + (apc.getPrice() - apc.getCost());
        }
        return prof;
    }
}

class JPA06_5 {
    public static void main(String args[]){
        Order ord = new Order();
        try {
            ord.in(new MiniNote());
            ord.in(new Note15());
            ord.in(new PC());
            //ord.in(new MultiPC(2, 4));
            //ord.in(new MultiPC(4, 2));
        } catch (Exception e) {
            System.out.println("This order exceeds 20000: " + ord.profit());
        }
    }
}
```

## 開始練習

```java
//...

class JPD06_5 {
    public static void main(String args[]){
        ...
            ord.in(new MiniNote());
            ord.in(new Note15());
            ord.in(new PC());

        ...
    }
}
```
