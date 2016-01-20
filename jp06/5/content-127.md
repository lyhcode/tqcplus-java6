# 題目二

(1)ITM學程，ITM的學生除了要修IT的課之外，
另外還需要修 acct 一門課。

(2)ITM 學生總平均成績的計算公式是：

    必修課的平均成績 * 0.4 + IT 課程的平均成績 * 0.4 + acct * 0.2 

(3)ITM學生選修課平均成績的計算公式是：

    (IT 課程的平均成績 + acct) / 2

(4)請 new 一位 ITM 的學生，並計算其「選修課平均成績」及「總平均成績」。

## 執行結果

```
Mary's elect score: 79.33 all score 83.07
```

## 程式碼

JPA06_2.java

```java
abstract class MIS {
    String name;
    int chi, eng;
    MIS(String n, int a, int b) {
        name = n;
        chi = a;
        eng = b;
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

public class JPA06_2 {
    public static void main(String argv[]) {
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        System.out.printf("Mary's elect score: %.2f all score %.2f\n", s3.averageElect(), s3.averageAll());
    }
}
```

## 開始練習

```java
...

public class JPD06_2 {
    public static void main(String argv[]) {
        MIS s3 = new ITM("Mary", 79, 88, 94, 92, 83, 69);
        System.out.printf("Mary's elect score: %.2f all score %.2f\n", s3.averageElect(), s3.averageAll());
    }
}
```
