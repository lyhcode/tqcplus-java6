# 題目三

1. 請比較一個Note15的筆電和一個PC類別的桌上型電腦何者較貴。

2. 請新增一個名為 AllPC 的類別，於此類別中撰寫isExpensive方法，此方法能夠比較何者的售價較貴，isExpensive傳回一個布林值。

顯示如 Screen Dump 參考畫面

![uml][1]


  [1]: http://yuml.me/7c1e4bc0

## 執行結果

```
Note15 is more expensive than PC

```

## 程式碼

JPA06_3.java

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

abstract class AllPC {    
	abstract public double getPrice();
	
    public boolean isExpensive(AllPC another){
	    if (this.getPrice() > another.getPrice()) {
	        return true;
	    }
        else {
            return false;
        }
	}
}

abstract class Desktop extends AllPC {
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

abstract class Notebook extends AllPC {
    LCD lcd;
    CPU cpu;
    HD hd;
    
    private int getPartCost() {
        return lcd.getCost()+cpu.getCost()+hd.getCost();
    }
    
    public double getCost() {
        return getPartCost() * 1.4;
    }
    
    public double getPrice() {
        return getPartCost() * 2.0;
    }
}

class MiniNote extends Notebook {
    public MiniNote() {
        lcd = new LCD(10);
        cpu = new CPU(1.66);
        hd = new HD(120);
    }
}

class Note15 extends Notebook {
    public Note15() {
        lcd = new LCD(15);
        cpu = new CPU(2.2);
        hd = new HD(160);
    }
}

class JPA06_3 {
    public static void main(String args[]) {
        PC pc = new PC();
        Note15 note15 = new Note15();
        
        if (pc.isExpensive(note15)) {
            System.out.println("PC is more expensive than Note15");
        }
        else {
            System.out.println("Note15 is more expensive than PC");
        }
    }
}
```

## 開始練習

```java
//...

class JPD06_3 {
    public static void main(String args[]) {
        PC pc = new PC();
        Note15 note15 = new Note15();
        ...
    }
}
```
