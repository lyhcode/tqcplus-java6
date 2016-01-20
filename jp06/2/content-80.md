# 題目一

<div class="alert alert-info">題目前後相關，請閱讀完這個題組的五個題目說明之後再作答，請務必讓每題答案皆能獨立執行。請將需要重複或共同使用的程式片段撰寫成函式，以供在類別中呼叫使用，避免在不同的類別中重複寫相同的程式碼，否則將酌量扣分。</div>

### 題目說明 ###

請開啟 JPD06_1.java，設計「電腦零件設計」程式。為電腦零件設計一個類別架構，請依下列題意完成作答。將 JPD06_1.java 內的 class JPD06_1 修改為 class JPA06_1，將檔案另存為 JPA06_1.java 後編譯為 JPA06_1.class，所有題目中有使用到類別也請編譯後一併儲存。

### 設計說明 ###

1. 請寫一個 LCD 類別。10吋的成本是 $2,000，15吋的成本是 $2,500，17吋的成本是 $3,000。
2. 請寫一個 CPU 類別。速度1.66的成本是6000，速度2.2的成本是8000，速度2.4的成本是11000。
3. 請寫一個 HD 類別。120G的成本是2400，160G的成本是2800。
4. 請使用以上的零件，撰寫以下的類別。 
5. 請寫一個MiniNote類別。一個MiniNote類別的筆電有一個10吋的LCD，一個速度1.66的CPU及一個120G的HD。
6. 請寫一個Note15類別。一個Note15類別的筆電有一個15吋的LCD，一個速度2.2的CPU及一個160G的HD。
7. 這兩型電腦的成本是其零件成本的1.4倍。定價則是其零件成本的2倍。
8. 請分別製造一個MinitNote及一個Note15，呼叫其getCost方法及getPrice方法，印出其傳回值。

![uml1][1]
![uml2][2]

  [1]: http://yuml.me/f43e4bd7
  [2]: http://yuml.me/87e0eb0f

## 執行結果

```
MiniNote cost:14559, price:20800
Note15 cost:18620, price:26600

```

## 程式碼

JPA06_1.java

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

abstract class Notebook {
    LCD lcd;
    CPU cpu;
    HD hd;
    
    private int getPartCost() {
        return lcd.getCost()+cpu.getCost()+hd.getCost();
    }
    
    public int getCost() {
        return (int)(getPartCost() * 1.4);
    }
    
    public int getPrice() {
        return (int)(getPartCost() * 2.0);
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

public class JPA06_1 {
    public static void main(String args[]) {
        MiniNote mininote = new MiniNote();
        System.out.println("MiniNote cost:"+mininote.getCost()+", price:"+mininote.getPrice());
        Note15 note15 = new Note15();
        System.out.println("Note15 cost:"+note15.getCost()+", price:"+note15.getPrice());
    }
}

```

## 開始練習

```java
//...

class JPD06_1 {
    public static void main(String args[]){
        MiniNote mininote = new MiniNote();
        System.out.println("MiniNote cost:"+mininote.getCost()+", price:"+mininote.getPrice());
        Note15 note15 = new Note15();
        System.out.println("Note15 cost:"+note15.getCost()+", price:"+note15.getPrice());        
    }
}
```
