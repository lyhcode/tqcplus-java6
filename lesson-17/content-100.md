# 題目二

續上題。

1. 不論專、兼任教師都需要繳交健保費100元及稅金。

   稅金 ＝ salary * 10%

2. 請寫一個命名為 afterTaxIns 的方法，以算出五位教師在扣除健保費與稅金後的薪資。
3. 該校增加一位行政主管（manager）的類別，行政主管必須是專任老師。
4. 行政主管分三級：rank = 1 or 2 or 3。

   其薪水的計算方式如下：
   salary = 專任教師的薪水 ＋ rank * 500

5. 請宣告一個名字是 Fang 的行政主管, 其 rate 是 500, totalHours 是 12, rank 是 3。請計算 Fang 的 salary 及 afterTaxIns(扣除健保費與稅金後的薪資)。

難

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
John-afterTaxIns: 620.0
Mary-afterTaxIns: 980.0
Peter-afterTaxIns: 3140.0
Paul-afterTaxIns: 2978.0
Eric-afterTaxIns: 4247.0
Fang-Manager: 7200.0
Fang-afterTax Ins: 6380.0
```

## 程式碼

JPA06_2.java

```java
import java.util.*;

abstract class Teacher {
    String name;
    int rate,totalHours;
    Teacher(String n,int r,int t){
        name = n;
        rate = r;
        totalHours = t;
    }
    abstract double salary();
    double getTax() {
        return this.salary() * 0.1;
    }
    double afterTaxIns() {
        return this.salary() - this.getTax() - 100;
    }
}

class PartTimeTeacher extends Teacher {
    PartTimeTeacher(String n,int r,int t) {
        super(n,r,t);
    }
    double salary(){
        return totalHours * rate;
    }
}

class FullTimeTeacher extends Teacher {
    FullTimeTeacher(String n,int r,int t) {
        super(n,r,t);
    }
    double salary() {
        return 9 * rate + ((totalHours - 9) * rate * 0.8);
    }
}

class Manager extends FullTimeTeacher {
    int rank;
    Manager(String n, int r, int t, int ra) {
        super(n,r,t);
        rank = ra;
    }
    double salary() {
        return super.salary() + rank * 500;
    }
}

public class JPA06_2 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        System.out.println("John-afterTaxIns: " + p1.afterTaxIns());
        System.out.println("Mary-afterTaxIns: " + p2.afterTaxIns());
        System.out.println("Peter-afterTaxIns: " + f1.afterTaxIns());
        System.out.println("Paul-afterTaxIns: " + f2.afterTaxIns());
        System.out.println("Eric-afterTaxIns: " + f3.afterTaxIns());

        Manager am1 = new Manager("Fang", 500, 12, 3);
        System.out.println("Fang-Manager: " + am1.salary());
        System.out.println("Fang-afterTax Ins: " + am1.afterTaxIns());

    }
}
```

## 開始練習

```java
...

public class JPD06_2 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        System.out.println("John-afterTaxIns: " + p1.afterTaxIns());
        System.out.println("Mary-afterTaxIns: " + p2.afterTaxIns());
        System.out.println("Peter-afterTaxIns: " + f1.afterTaxIns());
        System.out.println("Paul-afterTaxIns: " + f2.afterTaxIns());
        System.out.println("Eric-afterTaxIns: " + f3.afterTaxIns());

        Manager am1 = new Manager("Fang", 500, 12, 3);
        System.out.println("Fang-Manager: " + am1.salary());
        System.out.println("Fang-afterTax Ins: " + am1.afterTaxIns());

    }
}
```
