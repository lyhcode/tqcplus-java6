# Data Abstraction

設計一個 Timer 類別，在 Timer 類別中僅使用 second 變數保存時間記錄（秒數）。

 1. 實作 setSecond() 與 getSecond()
 2. 實作 setMinute() 與 getMinute()

## 執行結果

```
600秒
10分鐘
1500秒
25分鐘
900秒
15分鐘
```

## 程式碼

Main.java

```java
class Timer {
    int second;

    void setSecond(int s) {
        second = s;
    }

    int getSecond() {
        return second;
    }

    void setMinute(int m) {
        second = m * 60;
    }

    int getMinute() {
        return second / 60;
    }
}

public class Main {
    public static void main(String[] args) {
        Timer t = new Timer();

        t.setSecond(600);

        System.out.println(t.getSecond() + "秒");
        System.out.println(t.getMinute() + "分鐘");

        t.setSecond(1500);

        System.out.println(t.getSecond() + "秒");
        System.out.println(t.getMinute() + "分鐘");

        t.setMinute(15);

        System.out.println(t.getSecond() + "秒");
        System.out.println(t.getMinute() + "分鐘");
    }
}

```

## 開始練習

```java
class Timer {
    private int second;

    public void setSecond(int second) {
        this.second = second;
    }

    public int getSecond() {
        return second;
    }

    public void setMinute(int minute) {
        ___________________;
    }

    public int getMinute() {
        return __________________;
    }
}

public class Main {
    public static void main(String[] args) {
        Timer t = new Timer();

        t.setSecond(600);

        System.out.println(t.getSecond() + "秒");
        System.out.println(t.getMinute() + "分鐘");

        t.setSecond(______);

        System.out.println(t._________ + "秒");
        System.out.println(t._________ + "分鐘");

        t.setMinute(________);

        System.out.println(t._________ + "秒");
        System.out.println(t._________ + "分鐘");
    }
}
```
