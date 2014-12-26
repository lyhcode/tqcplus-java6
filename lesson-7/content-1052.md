# for-loop 實作練習 (1)

請利用 for-loop 搭配 if 條件判斷來設計一個 Java 程式，將 1 到 10 中的偶數輸出。

## 執行結果

```
1到10的偶數有：2
1到10的偶數有：4
1到10的偶數有：6
1到10的偶數有：8
1到10的偶數有：10
```

## 程式碼

Main.java

```java
public class Main {
    public static void main(String[] args) {
        for (int i=1; i<=10; i++) {
            if (i % 2 == 0) {
                System.out.println("1到10的偶數有：" + i);
            }
        }
    }
}
```

## 開始練習

```java
public class Main {
    public static void main(String[] args) {
        for (/*_____________*/) {
            if (/*_____________*/) {
                System.out.println("1到10的偶數有：" + i);
            }
        }
    }
}```
