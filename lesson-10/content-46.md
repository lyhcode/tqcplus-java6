# 404. 遞迴最大公因數

1. 請設計一個程式，持續輸入兩個數 m、n，使用遞迴計算 m 與 n 的最大公因數，直到 m 輸入的數值是 999 為止。
2. 程式執行時，顯示【Input m: 】要求輸入 m；輸入完畢，於下行顯示【Input n: 】要求輸入 n。
3. 計算最大公因數，顯示結果參考Screen Dump。

## 執行結果

```
Input m: 7
Input n: 49
最大公因數為: 7
Input m: 64
Input n: 128
最大公因數為: 64
Input m: 15
Input n: 10
最大公因數為: 5
Input m: 999
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        int num1, num2;
        System.out.print("Input m: ");
        num1 = keyboard.nextInt();
        while (num1 != 999) {
            System.out.print("Input n: ");
            num2 = keyboard.nextInt();
            System.out.println("最大公因數為: " + gcd(num1,num2));
            System.out.print("Input m: ");
            num1 = keyboard.nextInt();
        }
    }
    
    static int gcd(int m, int n) {
        if (n == 0) {
            return m;
        } else {
            return gcd(n, m % n);
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
        
      ...


    }
    
    ...
}```
