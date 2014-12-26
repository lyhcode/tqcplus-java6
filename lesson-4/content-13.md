# 103. 計算平均值

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 程式執行時，畫面顯示【Please input:】，於下方由鍵盤輸入3個整數，各整數中間空格鍵間隔，並分別存入三個整數變數。
2. 計算這三個整數的平均值，平均值請取到小數第二位。
3. 輸出平均值，執行結果顯示如 Screen Dump

## 執行結果

```
Please input:
3580 26400 13588
Average: 14522.67
```

## 程式碼

JPA01.java

```java
import java.util.*;

public class JPA01 {
    public static void main(String argv[]) {
        int a, b, c;

        System.out.println("Please input:");
    
        Scanner scanner = new Scanner(System.in);
        a = scanner.nextInt();
        b = scanner.nextInt();
        c = scanner.nextInt();

        System.out.printf("Average: %4.2f\n", (a + b + c) / 3.0);
    }
}
```

## 開始練習

```java
import java.util.*;

public class JPD01 {
    public static void main(String argv[]) {
        int a, __, c;

        System.out.println("Please input:");
    
        Scanner scanner = new Scanner(System.in);
        a = scanner.nextInt();
        b = _________________;
        c = scanner.nextInt();

        System.out.printf("____________\n", (a + b + c) / ___);
    }
}```
