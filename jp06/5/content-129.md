# 題目四

(1)請使用 HashMap 為該系設計建立一個 MISClass 類別。MISClass 的key值為學生姓名(String)，
value值為學生的物件，使其代入學生姓名後，可輸出該名學生的總平均成績，總平均成績依該學程有不同的計算方式，請參考第一題與第二題的公式。

(2)一個 MISClass 的實例即代表一個班級，並且有 put、list 兩個方法。

(3)使用 put 方法個別加入三名學生；在使用 list 方法印出該班所有學生的名字及總平均成績。

## 執行結果

```
Paul: 77.60
Mary: 83.07
John: 81.20
```

## 程式碼

JPA06_4.java

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
    
    void list() {
        for(String key : map.keySet()) {
            MIS value = map.get(key);
            System.out.printf("%s: %.2f\n", key, value.averageAll());
        }
    }
}

public class JPA06_4 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        MISClass c1 = new MISClass();
        c1.put("John", s1);
        c1.put("Paul", s2);
        c1.put("Mary", s3);
        c1.list();
    }
}
```

## 開始練習

```java
...

public class JPD06_4 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        MISClass c1 = new MISClass();
        c1.put("John", s1);
        c1.put("Paul", s2);
        c1.put("Mary", s3);
        c1.list();
    }
}
```
