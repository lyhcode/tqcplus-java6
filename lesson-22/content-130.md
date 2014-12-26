# 題目五

(1)請使用例外處理，將該班學生平均成績大於 100（代表資料錯誤）的學生姓名前增印兩個星號(**)，並結束程式。 

## 執行結果

```
**Peter: 257.6
```

## 程式碼

JPA06_5.java

```java
import java.util.*;

abstract class MIS {
    String name;
    int chi, eng;
    static int count = 0;
    MIS(String n, int a, int b) {
        name = n;
        chi = a;
        eng = b;
        count++;
    }
    
    static int getCount() {
        return count;
    }
    
    double averageReq() {
        return (chi + eng) / 2.0;
    }
  
    abstract double averageElect();
  
    double averageAll() {
        return averageElect() * 0.6 + averageReq() * 0.4;
    }
}

class IT extends MIS {
    int pl, db, ds;
    IT(String name, int chi, int eng, int a, int b, int c) {
        super(name, chi, eng);
        pl = a;
        db = b;
        ds = c;
    }
    double averageElect() {
        return (pl + db + ds) / 3.0;
    }
}

class ITM extends IT {
    int acct;
    ITM(String name, int chi, int eng, int a, int b, int c, int d) {
        super(name, chi, eng, a, b, c);
        acct = d;
    }
    
    double averageElect() {
        return (super.averageElect() + acct) / 2.0;
    }
    
    double averageAll() {
        return averageReq() * 0.4 + super.averageElect() * 0.4 + acct * 0.2;
    }
}

class IM extends MIS {
    int acct, econ;
    IM(String name, int chi, int eng, int a, int b) {
        super(name, chi, eng);
        acct = a;
        econ = b;
    }
    double averageElect() {
        return (acct + econ) / 2.0;
    }
}

class MISClass {
    HashMap<String, MIS> map;
    
    MISClass () {
        map = new HashMap<String, MIS>();
    }
    
    void put(String name, MIS obj) {
        map.put(name, obj);
    }
    
    void list() throws scoreHighException {
        for (String key : map.keySet()) {
            MIS value = map.get(key);
            if (value.averageAll() > 100) {
                throw new scoreHighException(key, value.averageAll());
            } 
        }
    }
}

class scoreHighException extends Exception {
    String name;
    double avg;
    
    scoreHighException(String n, double a) {
        name = n;
        avg = a;
    }
    
    public String getMessage() {
        return "**" + name + ": " + avg;
    }
}

public class JPA06_5 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        MISClass c1 = new MISClass();
        c1.put("John", s1);
        c1.put("Paul", s2);
        c1.put("Mary", s3);
        c1.put("Peter", new IM("Peter", 89, 980, 77, 69));
        try {
            c1.list();
        } catch (scoreHighException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

## 開始練習

```java
...

public class JPD06_5 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        MISClass c1 = new MISClass();
        c1.put("John", s1);
        c1.put("Paul", s2);
        c1.put("Mary", s3);
        c1.put("Peter", new IM("Peter", 89, 980, 77, 69));
        ...
    }
}
```
