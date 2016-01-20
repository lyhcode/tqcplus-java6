# 題目一

(1)MIS 有 IT 與 IM 兩個學程。MIS 學生的共同必修課為 chi, eng。
IT 的選修課有：pl, db, ds；IM 的選修課有：econ, acct。

(2)學生總平均成績為必修課平均成績佔40%，選修課平均成績佔60%，計算公式是：必修課的平均成績 * 0.4 + 選修課的平均成績 * 0.6。

(3)請 new 兩位學生的資料並計算其「選修課的平均成績」及「總平均成績」。


## 執行結果

```
John's elect score: 76.00 all 81.20
Paul's elect score: 72.00 all 77.60
```

## 程式碼

JPA06_1.java

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

public class JPA06_1 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        System.out.printf("John's elect score: %.2f all %.2f\n", s1.averageElect(), s1.averageAll());
        System.out.printf("Paul's elect score: %.2f all %.2f\n", s2.averageElect(), s2.averageAll());
    }
}
```

## 開始練習

```java
...

public class JPD06_1 {
    public static void main(String argv[]) {
        MIS s1 = new IT("John", 88, 90, 76, 68, 84);
        MIS s2 = new IM("Paul", 92, 80, 76, 68);
        System.out.printf("John's elect score: %.2f all score %.2f\n", s1.averageElect(), s1.averageAll());
        System.out.printf("Paul's elect score: %.2f all score %.2f\n", s2.averageElect(), s2.averageAll());
    }
}
```
