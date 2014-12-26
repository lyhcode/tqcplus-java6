# 遞迴實作練習 (2)

請設計 star 遞迴函式，傳遞一個整數參數「n」，印出 n 個「*」符號。

## 執行結果

```
*****
****
***
**
*

```

## 程式碼

Main.java

```java
public class Main {
    
    public static void main(String[] args) {
        for (int i = 5; i > 0; i--) {
            star(i);
        }
    }
    
    static void star(int n) {
        if (n > 0) {
            System.out.print("*");
            star(n - 1);
        }
        else {
            System.out.println();
        }
    }
}

```

## 開始練習

```java
public class Main {
    
    public static void main(String[] args) {
        for (int i = 5; i > 0; i--) {
            star(i);
        }
    }
    
    static void star(int n) {
        // 撰寫程式
    }
}
```
