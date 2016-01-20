# 題目二

1. 根據上題說明，依 SalaryWorker、HourlyWorker、Manager 順序先印出此三位的該月收入。
2. 請寫一方法，首先比較SalaryWorker 與 HourlyWorker 兩者的該月收入，何者較高；再比較HourlyWorker與Manager的月收入何者較高，並接續列印薪資較高的員工代號，顯示【員工代號+較高】。
3. 再請計算每位員工該月的應繳稅額，稅率均為薪水的15%，分別列出SalaryWorker、HourlyWorker、Manager 的稅額。

## 執行結果

```
SalaryWorker：15000.0
HourlyWorker：16000.0
Manager：25000.0
96002較高
97001較高
SalaryWorker稅額：2250.0
HourlyWorker稅額：2400.0
Manager稅額：3750.0
```

## 程式碼

JPA06_2.java

```java
abstract class Employee {
    String id;
    double pay;
    Employee(String i) {
        id = i;
    }
    abstract double monthPay();
    String whichHigh(Employee e) {
        if (monthPay() > e.monthPay()) {
            return id + "較高";
        } else {
            return e.id + "較高";
        }
    }
    double monthTaxes() {
        return monthPay() * 0.15;
    }
}

class SalaryWorker extends Employee {
    int salary;
    SalaryWorker(String i,int s) {
        super(i);
        salary = s;
     }
     double monthPay( ){
         pay = salary / 12;
         return pay;
     }
}

class HourlyWorker extends Employee {
   int money;
   int hour;
 
   HourlyWorker(String i, int m, int h) {
       super(i);
       money = m;
       hour = h;
   }
 
   double monthPay() {
       pay = hour * money;
       return pay;
   }
}

class Manager extends SalaryWorker {
    int bonus;
    Manager(String i,int s, int b) {
        super(i, s);
        bonus = b;
    }
    double monthPay() {
        pay = super.monthPay() + bonus;
        return pay;
    }
}

public class JPA06_2 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);     
        System.out.println("SalaryWorker："+sw1.monthPay());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker："+hw1.monthPay());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager："+ma1.monthPay());

        System.out.println(sw1.whichHigh(hw1));
        System.out.println(hw1.whichHigh(ma1));

        System.out.println("SalaryWorker稅額："+sw1.monthTaxes());
        System.out.println("HourlyWorker稅額："+hw1.monthTaxes());
        System.out.println("Manager稅額："+ma1.monthTaxes());    
    }
}
```

## 開始練習

```java
...

public class JPD06_2 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);     
        System.out.println("SalaryWorker："+sw1.monthPay());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker："+hw1.monthPay());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager："+ma1.monthPay());

        ...

        System.out.println("SalaryWorker稅額："+sw1.monthTaxes());
        System.out.println("HourlyWorker稅額："+hw1.monthTaxes());
        System.out.println("Manager稅額："+ma1.monthTaxes());     
    }
}
```
