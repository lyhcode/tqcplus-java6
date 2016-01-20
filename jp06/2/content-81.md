# 題目二

1. 請寫一個PC類別，一個PC類別的桌上型電腦有一個速度2.4的CPU及一個160G的HD。製造一個PC類別的桌上型電腦的成本是「零件成本」加500，售價則為「零件成本」的1.8倍。
2. 另請寫一個MultiPC類別，一個MultiPC的超級電腦，可以有多顆2.4G的CPU及多顆160G的HD。 MultiPC的成本為其「零件成本」的1.2倍，售價則為「零件成本」的1.8倍。
3. 請製造一個PC類別的桌上型電腦，一個2顆CPU及4顆HD的MultiPC及一個4顆CPU及8顆HD的MultiPC. 
4. 分別呼叫其getCost方法及getPrice方法，印出其傳回值。

![uml][1]

  [1]: http://yuml.me/f5f479a3

## 執行結果

```
PC cost:14300.0, price:24840.0
MultiPC: 2CPU, 4HD, cost:39840.0, price:59760.0
MultiPC: 4CPU, 8HD, cost:79680.0, price:119520.0
```

## 程式碼

JPA06_2.java

```java
abstract class Part {
    int cost;
    
    public int getCost() {
        return cost;
    }
}

class LCD extends Part {
    int inch;
    
    public LCD(int inch) {
        this.inch = inch;
        
        switch (inch) {
        	case 10:
                this.cost = 2000;
            break;
            case 15:
                this.cost = 2500;
            break;
            case 17:
                this.cost = 3000;
            break;
        }
    }
}

class CPU extends Part {
    double speed;
    
    public CPU(double speed) {
        this.speed = speed;
        
        if (speed == 1.66) {
            this.cost = 6000;
        }
        else if (speed == 2.2) {
	        this.cost = 8000;
        }
        else if (speed == 2.4) {
            this.cost = 11000;
        }
    }
}

class HD extends Part {
    int size;
    
    public HD(int size) {
    	this.size = size;
        
        switch (size) {
            case 120:
            	this.cost = 2400;
            break;
            case 160:
            	this.cost = 2800;
            break;
        }
    }
}

abstract class Desktop {
    CPU cpu;
    HD hd;
    
    int cpuNo = 1;
    int hdNo = 1;
    
    public double getPartCost() {
        return (cpu.getCost() * cpuNo + hd.getCost() * hdNo);
    }
    
    public double getPrice() {
        return getPartCost() * 1.8;
    }
}

class PC extends Desktop {    
    public PC() {
        cpu = new CPU(2.4);
        hd = new HD(160);
    }
    
    public double getCost() {
        return getPartCost() + 500;
    }
}

class MultiPC extends Desktop {
    public MultiPC(int cpuNo, int hdNo) {
        cpu = new CPU(2.4);
        hd = new HD(160);
        this.cpuNo = cpuNo;
        this.hdNo = hdNo;
    }
    
    public double getCost() {
        return getPartCost() * 1.2;
    }
}

class JPA06_2 {
    public static void main(String args[]){
        PC pc = new PC();
        System.out.println("PC cost:"+pc.getCost()+", price:"+pc.getPrice());
        MultiPC multipc1 = new MultiPC(2, 4);
        System.out.println("MultiPC: 2CPU, 4HD, cost:"+multipc1.getCost()+", price:"+multipc1.getPrice());
        MultiPC multipc2 = new MultiPC(4, 8);
        System.out.println("MultiPC: 4CPU, 8HD, cost:"+multipc2.getCost()+", price:"+multipc2.getPrice());
    }
}
```

## 開始練習

```java
//...

class JPD06_2 {
    public static void main(String args[]){
        PC pc = new PC();
        System.out.println("PC cost:"+pc.getCost()+", price:"+pc.getPrice());
        MultiPC multipc1 = new MultiPC(2, 4);
        System.out.println("MultiPC: 2CPU, 4HD, cost:"+multipc1.getCost()+", price:"+multipc1.getPrice());
        MultiPC multipc2 = new MultiPC(4, 8);
        System.out.println("MultiPC: 4CPU, 8HD, cost:"+multipc2.getCost()+", price:"+multipc2.getPrice());
    }
}
```
