# 401. 遞迴階乘計算

1. 請寫一個程式輸入一個數n，使用遞迴計算n的階乘，直到n輸入的數值是999為止。
2. 程式執行時，顯示【Input n (0 <= n <= 16):】要求輸入數值。
3. 顯示結果參考Screen Dump。

教學用補充內容：以下是這個程式執行過程的範例：

    fac(3);
    =>return (3 * fac(2))
    =>return (3 * return (2 * fac(1)) )
    =>return (3 * return (2 * return (1 * fac(0)) ) )
    =>return (3 * 2)
    =>6

## 執行結果

```
Input n (0 <= n <= 16):6
6 的階乘 = 720
Input n (0 <= n <= 16):10
10 的階乘 = 3628800
Input n (0 <= n <= 16):999
```

## 程式碼

JPA04.java

```java
import java.util.*;

public class JPA04 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String args[]) {
        int n = -1;
        
        while (n != 999) {
            System.out.print("Input n (0 <= n <= 16):");
            n = keyboard.nextInt();
            
            if (n != 999) {
                 System.out.printf("%d 的階乘 = %d\n", n, fac(n));
            }
        }
    }
    
    static int fac(int n) {
        if (n == 0) {
            return 1;
        }
        else {
            return (n * fac(n - 1));
        }
    }
}
```

## 開始練習

```java
import java.util.*;

public class JPD04 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String args[]) {
        // 撰寫程式
    }
}```
