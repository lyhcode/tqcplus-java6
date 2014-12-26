# 402. 尾端遞迴階乘計算

1. 尾端遞迴程式的特性是以另外傳入的參數來累計遞迴的答案。
2. 請寫一個程式持續輸入一個數 n，請個別使用尾端遞迴及迴圈，計算 n 的階乘，直到 n 輸入的數值是 999 為止。
3. 程式執行時，顯示【Input n (0 <= n <= 16):】要求輸入數值。
4. 顯示結果參考 Screen Dump。

## 執行結果

```
Input n (0 <= n <= 16):6
6 的階乘(尾端遞迴) = 720
6 的階乘(迴圈) = 720
Input n (0 <= n <= 16):8
8 的階乘(尾端遞迴) = 40320
8 的階乘(迴圈) = 40320
Input n (0 <= n <= 16):999
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int num1;
        System.out.print("Input n (0 <= n <= 16):");
        num1 = keyboard.nextInt();
        while (num1 != 999) {
            System.out.printf("%d 的階乘(尾端遞迴) = %d\n", num1, facTail(num1, 1));
            System.out.printf("%d 的階乘(迴圈) = %d\n", num1, facLoop(num1, 1));
            System.out.print("Input n (0 <= n <= 16):");
            num1 = keyboard.nextInt();
        }
    }
    
    static int facTail(int n, int r) {
        if (n == 0) {
            return r;
        } else {
            return facTail((n - 1), (r * n)); 
        }
    }
    
    static int facLoop(int n, int r) {
        while (n != 0) {
            r = r * n;
            n = n - 1; 
        }
        return r;
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int num1;
        System.out.print("Input n (0 <= n <= 16):");
        num1 = keyboard.nextInt();
        while (num1 != 999) {
            System.out.printf("%d 的階乘(尾端遞迴) = %d\n", num1, facTail(num1, 1));
            System.out.printf("%d 的階乘(迴圈) = %d\n", num1, facLoop(num1, 1));
            System.out.print("Input n (0 <= n <= 16):");
            num1 = keyboard.nextInt();
        }
    }
    
    static int facTail(int n, int r) {
        if(n == 0) {
            return r;
        } else {
            return facTail((n - 1), ________); 
        }
    }
    
    static int facLoop(int n, int r) {
        ...
    }
}```
