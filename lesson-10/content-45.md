# 403. 尾端遞迴次方計算

1. 請寫一個程式持續輸入兩個數 m、n，使用尾端遞迴及迴圈計算 m 的 n 次方，直到 m 輸入的數值是 999 為止。
2. 程式執行時，顯示【Input m:】要求輸入 m；輸入完畢，於下行顯示【Input n:】要求輸入 n。
3. 顯示結果參考Screen Dump。

## 執行結果

```
Input m:3
Input n:6
Ans（尾端遞迴）: 729
Ans（迴圈）: 729
Input m:12
Input n:3
Ans（尾端遞迴）: 1728
Ans（迴圈）: 1728
Input m:999
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int num1, num2;
        System.out.print("Input m:");
        num1 = keyboard.nextInt();
        while (num1 != 999) {
            System.out.print("Input n:");
            num2 = keyboard.nextInt();
            System.out.println("Ans（尾端遞迴）: " + powerTail(num1,num2, 1));
            System.out.println("Ans（迴圈）: " + powerLoop(num1,num2, 1));
            System.out.print("Input m:");
            num1 = keyboard.nextInt();
        }
    }
    
    static int powerTail(int m, int n, int r) {
        if (n == 0) {
            return r;
        } else {
            return powerTail(m, n - 1, m * r);
        }
    }
    
    static int powerLoop(int m, int n, int r) {
        while (n != 0) {
            n = n - 1;
            r = m * r;
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
        

       ...

        }
    }
    
    ...


}```
