# 題目四

續上題。

1. 請使用 HashMap 撰寫一個能夠存放教師資料的類別，HashMap的key值為老師名稱(String)，value值為該老師物件。
2. 將這些教師物件存入一個由這個類別所製造的實例中，然後撰寫一個totalOfAll方法，將所有老師個別的稅後薪資(afterTaxIns)相加，輸出總和。

中：程式及輸出全部正確使給分。

## 執行結果

```
Total salary: 18345.0
```

## 程式碼

JPA06_4.java

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

class TeacherDB {
    HashMap<String, Teacher> map;
    
    TeacherDB() {
        map = new HashMap<String, Teacher>();
    }
    
    void store(String name, Teacher t) {
        map.put(name, t);
    }
    
    double totalOfAll() {
        double total = 0;
        for (Teacher t : map.values()) {
            total += t.afterTaxIns();
        }
        return total;
    }
}
        
public class JPA06_4 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);
    
        TeacherDB school = new TeacherDB();
        school.store("John", p1);
        school.store("Mary", p2);
        school.store("Peter", f1);
        school.store("Paul", f2);
        school.store("Eric", f3);
        school.store("Fang", am1);
        System.out.println("Total salary: " + school.totalOfAll());
    }
}
```

## 開始練習

```java
...

public class JPD06_4 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);
    
        TeacherDB school = new TeacherDB();
        school.store("John", p1);
        school.store("Mary", p2);
        school.store("Peter", f1);
        school.store("Paul", f2);
        school.store("Eric", f3);
        school.store("Fang", am1);
        System.out.println("Total salary: " + school.totalOfAll());
    }
}
```
