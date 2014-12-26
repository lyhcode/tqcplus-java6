# 題目四

1. 請使用 ``LinkedList`` 為這家工廠寫一個 Order 類別。

2. 某次 order 的資料如下：

        MiniNote 1台
        Note15   1台
        PC       1台

3. 請寫一 revenue 方法，輸出賣出這些電腦的總收入。 


## 執行結果

```
72240.0
```

## 程式碼

JPA06_4.java

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
    int getPartCost(){
        return (lcd.getCost()+cpu.getCost()+hd.getCost());
    }
    double getCost(){
        return getPartCost() * 1.4;
    }
    double getPrice(){
        return getPartCost() * 2.0;
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

class PC extends PCandMultiPC {
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
    double revn=0;
    LinkedList<AllPC> pcs = new LinkedList<AllPC>();
    
    void in(AllPC allpc){
        pcs.add(allpc);
    }
    
    double revenue() {
        double revn = 0;
        for (AllPC apc: pcs) {
           revn = revn + apc.getPrice();
        }
        return revn;
    }
}

class JPA06_4 {
    public static void main(String args[]){
        Order ord = new Order();
        ord.in(new MiniNote());
        ord.in(new Note15());
        ord.in(new PC());
        System.out.println(ord.revenue());
    }
}
```

## 開始練習

```java
//...

class JPD06_4 {
    public static void main(String args[]){
        Order ord = new Order();
        ord.in(new MiniNote());
        ord.in(new Note15());
        ord.in(new PC());
        System.out.println(ord.revenue());
    }
}
```
