# 題目四

1. 請使用 HashMap 寫一個 Management 人事管理類別，Management 提供一個能夠傳入員工編號，然後傳回該員工稅後薪資的方法 afterTax。
2. 請查詢 97001 的稅後薪資。

## 執行結果

```
97001 的稅後薪資： 21250.0
```

## 程式碼

JPA06_4.java

```java
import java.util.*;

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

class Management {
    Map<String, Employee> map = new HashMap<String, Employee>();
    
    void put(String id, Employee e) {
        map.put(id, e);
    }
    
    double afterTax(String id) {
        Employee e = (Employee)map.get(id);
        return e.monthPay() - e.monthTaxes();
    }
}

public class JPA06_4 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);        
        Manager ma1 = new Manager("97001", 240000, 5000);        
        Management m = new Management();
        m.put("96001", sw1);
        m.put("96002", hw1);
        m.put("97001", ma1);
        System.out.println("97001 的稅後薪資： " + m.afterTax("97001"));
    }
}
```

## 開始練習

```java
...

public class JPD06_4 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);        
        Manager ma1 = new Manager("97001", 240000, 5000);        
        Management m = new Management();
        m.put("96001", sw1);
        m.put("96002", hw1);
        m.put("97001", ma1);
        System.out.println("97001 的稅後薪資： " + m.afterTax("97001"));
    }
}
```
