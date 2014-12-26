# 加總函式（SUM）

定義一個加總函式 sum，以遞迴方式設計。

測試案例：

1. ```sum("12") //=> 3```
2. ```sum("123") //=> 6```
3. ```sum("1234") //=> 10```

觀察以上的執行狀況，呼叫 sum 的遞迴呼叫也是內涵（embedded）在加總算式 (Integer.parseInt(str.substring(0, 1)) + ...) 之內。而程式的執行結果是在最後一個遞迴呼叫 sum("") 完成後才依序累加 (1 + (2 + (3 + (4 + 0)))) 而得的。這是內涵式遞迴的另一個例子。

## 執行結果

```
10
```

## 程式碼

Recursive.java

```java
public class Recursive {
    public static void main(String args[]) {
        System.out.println(sum("1234"));
    }

    public static int sum(String str) {
        if (str.equals(""))
            return 0;
        else
            return  Integer.parseInt(str.substring(0, 1)) + sum(str.substring(1));
    }
}

```

## 開始練習

```java
public class Recursive {
    public static void main(String args[]) {
        System.out.println(sum("1234"));
    }

    public static int sum(String str) {
        // ...
    }
}
```
