# 102. 單位換算

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 程式執行時，畫面顯示【Please input:】，於後方由鍵盤輸入數字後，輸出轉換數值(由公斤轉換成磅數)，執行結果顯示如 Screen Dump。
2. 單位轉換公式為：1公斤等於2.20462磅。

## 執行結果

```
Please input: 15
15.000000 kg = 33.069300 ponds
```

## 程式碼

JPA01.java

```java
import java.util.Scanner;
public class JPA01 {
    public static void main(String[] args) {
        Scanner keyboard = new Scanner(System.in);
        System.out.print("Please input: ");
        double kilo, pound;
        kilo = keyboard.nextDouble();
        pound = kilo * 2.20462;
        System.out.printf("%f kg = %f ponds\n", kilo, pound);
    }
}
```

## 開始練習

```java
import java.util.Scanner;
public class JPD01 {
    public static void main(String[] args) {
        Scanner keyboard = new Scanner(System.in);
        System.out.print("Please input: ");
        double kilo, pound;
        kilo = keyboard.nextDouble();
        pound = _______________;
        System.out.printf("%f kg = %f ponds\n", _____, _____);
    }
}```
