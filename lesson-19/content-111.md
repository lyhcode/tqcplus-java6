# 題目三

1. 請以類別變數累計員工人數，並在每次計算某一員工的月繳稅額時，以類別變數累計總月繳稅額。
2. 撰寫一個能夠傳回所有員工的平均繳稅金額的類別方法。

## 執行結果

```
SalaryWorker稅額：2250.0
HourlyWorker稅額：2400.0
Manager稅額：3750.0
平均稅額：2800.0
```

## 程式碼

JPA06_3.java

```java
abstract class Employee {
    String id;
    double pay;
    static double totalTax = 0.0;
    static int count = 0;
    
    Employee(String i) {
        id = i;
        count++;
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
        double tax;
        
        tax = monthPay() * 0.15;
        totalTax = totalTax + tax; 
        return monthPay() * 0.15;
    }
    
    static double getAverageTax() {
        return totalTax / count;
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

public class JPA06_3 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        System.out.println("SalaryWorker稅額："+sw1.monthTaxes());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker稅額："+hw1.monthTaxes());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager稅額："+ma1.monthTaxes());    
        
        System.out.println("平均稅額："+Employee.getAverageTax());
    }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        System.out.println("SalaryWorker稅額："+sw1.monthTaxes());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker稅額："+hw1.monthTaxes());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager稅額："+ma1.monthTaxes());    
        
        System.out.println("平均稅額："+Employee.getAverageTax());
    }
}
```
