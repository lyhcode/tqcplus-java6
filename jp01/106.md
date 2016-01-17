# 106. 數學函數

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 有一數學函數 f(x) = 3x^3 + 2x - 1。
2. 請撰寫一函數 f 用來傳回 f(x) 的值，並分別計算 f(-3.2)、f(-2.1)、f(0)、與 f(2.1)。
3. 函數 f(x) 值取到小數第四位。
4. 依此數學函數計算，分別輸出此四個計算值，執行畫面顯示如 Screen Dump。

## 執行結果

```
f(-3.2) = -105.7040
f(-2.1) = -32.9830
f(0) = -1.0000
f(2.1) = 30.9830

```

## 程式碼

JPA01.java

```java
public class JPA01 {
    public static void main(String args[]) {
        System.out.printf("f(-3.2) = %.4f\n", f(-3.2));
        System.out.printf("f(-2.1) = %.4f\n", f(-2.1));
        System.out.printf("f(0) = %.4f\n", f(0));
        System.out.printf("f(2.1) = %.4f\n", f(2.1));
    }
    static double f(double x) {
        return (3 * x * x * x + 2 * x - 1);
    }
}
```

## 開始練習

```java
public class JPD01 {
    public static void main(String args[]) {
        System.out.printf("f(-3.2) = %.4f\n", f(-3.2));
        System.out.printf("f(-2.1) = %.4f\n", f(-2.1));
        System.out.printf("f(0) = %.4f\n", f(0));
        System.out.printf("f(2.1) = %.4f\n", f(2.1));
    }
    static _________ f(double x) {
        ____________________________;
    }
}```
