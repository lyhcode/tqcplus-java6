# 題目五

續上題。

1. 撰寫一個能夠印出五位教師（不含行政主管Fang）的姓名及薪資(不扣稅及不扣健保費)的方法。這個方法利用例外處理將薪水少於1500的教師姓名前印出兩個**號。

中：程式及輸出全部正確使給分。

## 執行結果

```
Paul 3420.0
**Mary 1200.0
Eric 4830.0
Peter 3600.0
**John 800.0
```

## 程式碼

JPA06_5.java

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

class lessSalaryException extends Exception {
    String name;
    double salary;
    lessSalaryException(String n, double s) {
        name = n;    salary = s;
    }   
    public String getMessage() {
        return "**" + name + " " + salary;
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
    
    void printAllTeacher() {
        for (String key : map.keySet()) {
            try {
                Teacher t = map.get(key);
                if (t.salary() < 1500) {    
                    throw new lessSalaryException(t.name, t.salary());
                } else {
                    System.out.println(t.name + " " + t.salary());
                }
            } catch (lessSalaryException lse) {
                System.out.println(lse.getMessage());
            }
        }
    }
}
        
public class JPA06_5 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        TeacherDB school = new TeacherDB();
        school.store("Paul", f2);
        school.store("Mary", p2);
        school.store("Eric", f3);
        school.store("Peter", f1);
        school.store("John", p1);
       
        school.printAllTeacher();
    }
}
```

## 開始練習

```java
...

public class JPD06_5 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        TeacherDB school = new TeacherDB();
        school.store("Paul", f2);
        school.store("Mary", p2);
        school.store("Eric", f3);
        school.store("Peter", f1);
        school.store("John", p1);
       
        school.printAllTeacher();
    }
}
```
