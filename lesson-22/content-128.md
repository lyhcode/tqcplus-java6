# 題目三

(1)請以類別變數累計學生人數，並呼叫一個方法傳回該系的學生人數。

## 執行結果

```
Total students: 3
```

## 程式碼

JPA06_3.java

```java
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

public class JPA06_3 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        System.out.println("Total students: " + MIS.getCount());
    }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        System.out.println("Total students: " + __________);
    }
}
```
