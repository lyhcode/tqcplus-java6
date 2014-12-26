# 題目一

請以避免在不同類別中重複寫相同的程式碼的設計方式，撰寫這一題的程式。

1. 某校有兩種類別的老師：專任老師(FullTime)及兼任老師(PartTime)。
2. 專任老師有以下的資料：name、rate（每小時標準工資）、 totalHours。
3. 專任老師薪水的計算方式為：

   其薪水的計算方式如下： salary = 9 * rate + ((totalHours – 9) * rate * 0.8)。 

4. 兼任老師有以下的資料：name、rate（每小時標準工資）、totalHours。
5. 兼任老師薪水的計算方式為：salary = totalHours * rate。
6. 請為此學校新增兩名兼任老師及三名專任老師，並印出這五位教師的薪資。

難

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
John-PartTime: 800.0
Mary-PartTime: 1200.0
Peter-FullTime: 3600.0
Paul-FullTime: 3420.0
Erit-FullTime: 4830.0
```

## 程式碼

JPA06_1.java

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

public class JPA06_1 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        System.out.println("John-PartTime: " + p1.salary());
        System.out.println("Mary-PartTime: " + p2.salary());
        System.out.println("Peter-FullTime: " + f1.salary());
        System.out.println("Paul-FullTime: " + f2.salary());
        System.out.println("Erit-FullTime: " + f3.salary());
    }
}
```

## 開始練習

```java
...

public class JPD06_1 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        System.out.println("John-PartTime: " + p1.salary());
        System.out.println("Mary-PartTime: " + p2.salary());
        System.out.println("Peter-FullTime: " + f1.salary());
        System.out.println("Paul-FullTime: " + f2.salary());
        System.out.println("Erit-FullTime: " + f3.salary());
    }
}
```
