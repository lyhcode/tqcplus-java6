# 求最大公因數

最大公因數（Greatest Common Divisor，簡寫為G.C.D.；或Highest Common Factor，簡寫為H.C.F.），指某幾個整數共有因數中最大的一個。

最大公因數的使用 while 迴圈的寫法如下：

    private static int gcd(int m, int n) { 
        int r = 0;
    
        while(n != 0) { 
            r = m % n; 
            m = n; 
            n = r; 
        }
    
        return m; 
    }

請設計遞迴方法求出最大公因數。

## 執行結果

```
輸入兩數: 
m = 10 
n = 5 
GCD: 5
```

## 程式碼

UseRecursion.java

```java
import java.util.Scanner;
 
public class UseRecursion { 
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
 
        System.out.println("輸入兩數:"); 
        System.out.print("m = "); 
        int m = scanner.nextInt();
        System.out.print("n = "); 
        int n = scanner.nextInt();
        System.out.println("GCD: " + gcd(m, n)); 
    } 
 
    private static int gcd(int m, int n) { 
        if(n == 0) 
            return m; 
        else 
            return gcd(n, m % n); 
    } 
}
```

## 開始練習

```java
import java.util.Scanner;
 
public class UseRecursion { 
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
 
        System.out.println("輸入兩數:"); 
        System.out.print("m = "); 
        int m = scanner.nextInt();
        System.out.print("n = "); 
        int n = scanner.nextInt();
        System.out.println("GCD: " + gcd(m, n)); 
    } 
 
    private static int gcd(int m, int n) { 
        // 請完成程式碼
    }
}```
