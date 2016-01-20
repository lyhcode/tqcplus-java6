# 題目一

1. 該工廠有三種類別的員工。
2. SalaryWorker 以「年薪」（月薪為年薪除以12）計算薪水。
3. HourlyWorker 以「時薪」計算薪水。
4. Manager 必須是 SalaryWorker，但是除了年薪之外，每月還有紅利。
5. 每名員工都有編號。
6. 請宣告一個 SalaryWorker 類別。其員工編號為 96001，年薪為180000，撰寫 monthPay 方法以計算這名員工該月的收入。
7. 請宣告一個 HourlyWorker類別。其員工編號為 96002，每月工時160小時，時薪100，撰寫monthPay方法計算這名員工該月的收入。
8. 請宣告一個Manager類別。其員工編號為 97001，年薪為 240000，每月的紅利為 5000，撰寫 monthPay方法計算這名員工該月的收入。
9. 請分別顯示三位員工的薪水，顯示結果如Screen Dump。

## 執行結果

```
SalaryWorker：15000.0
HourlyWorker：16000.0
Manager：25000.0
```

## 程式碼

JPA06_1.java

```java
abstract class Employee {
    String id;
    double pay;
    Employee(String i) {
        id = i;
    }
    abstract double monthPay();
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

public class JPA06_1 {
    public static void main(String argv[]) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        System.out.println("SalaryWorker："+sw1.monthPay());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker："+hw1.monthPay());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager："+ma1.monthPay());
    }
}
```

## 開始練習

```java
// 請完成本題各類別程式設計

public class JPD06_1 {
    public static void main(String[] args) {
        SalaryWorker sw1 = new SalaryWorker("96001",180000);
        System.out.println("SalaryWorker："+sw1.monthPay());
        HourlyWorker hw1 = new HourlyWorker("96002", 100, 160);
        System.out.println("HourlyWorker："+hw1.monthPay());
        Manager ma1 = new Manager("97001", 240000, 5000);
        System.out.println("Manager："+ma1.monthPay());
    }
}```
