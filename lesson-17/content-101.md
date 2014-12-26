# 題目三

續上題。

1. 請寫一個比較兩位教師，那一位薪水較高的方法。
2. 比較 Fang 與 Eric 哪一位薪水(未扣除健保費與稅金前的薪水)較高？
3. 比較 Eric 與 John 哪一位薪水(未扣除健保費與稅金前的薪水)較高？

中

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
Fang is higher than Eric
Eric is higher than John
```

## 程式碼

JPA06_3.java

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
    String getName() {
        return name;
    }
    void compare(Teacher that) {
        if (this.salary() > that.salary()) {
            System.out.printf("%s is higher than %s\n", this.getName(), that.getName()); 
        } else {
            System.out.printf("%s is higher than %s\n", that.getName(), this.getName());
        }
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

public class JPA06_3 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);

        am1.compare(f3);
        p1.compare(f3);
    }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);

        am1.compare(f3);
        p1.compare(f3);
    }
}
```
