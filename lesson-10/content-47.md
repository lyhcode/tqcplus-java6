# 405. 遞迴函數

1. 請利用下面的公式，撰寫遞迴函數 sum2：
    - sum2(1) = 2
    - sum2(n) = sum2(n - 1) + 2 * n
2. 程式執行時，顯示【Input n:】要求輸入 n (n>=1)，並將 n 值代入函數中。
3. 顯示結果參考Screen Dump。

## 執行結果

```
Input the number n: 50
Ans: 2550
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int n; 
        System.out.print("Input the number n: ");
        n = keyboard.nextInt();
        System.out.printf("Ans: %d\n",sum2(n));
    }
    
    static int sum2(int n) {
        if (n == 1) {
            return 2;
        } else {
            return (sum2(n - 1) + 2 * n);
        }
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int n; 
        System.out.print("Input the number n: ");
        n = keyboard.nextInt();
        System.out.printf("Ans: %d\n",sum2(n));
    }
    
    static int sum2(int n) {
        if (n == 1) {
            return 2;
        } else {
            return (sum2(n - 1) + 2 * n);
        }
    }
}```
