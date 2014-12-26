# 310. 迴圈正偶數相加

1. 試利用 do-while 迴圈，計算 2 + 4 + 6 + ... + n 的總和，其中 n 為一由鍵盤輸入的正偶數，若輸入的不是正偶數，則程式會要求使用者再次輸入，直到輸入的數是正偶數為止。
2. 請參考標準輸出的執行結果。

註解：取得鍵盤輸入與計算總合皆使用 do-while 迴圈。

程式及輸出全部正確使給分。

## 執行結果

```
請輸入 n 的值 (n > 0，且為偶數): 3
請輸入 n 的值 (n > 0，且為偶數): -2
請輸入 n 的值 (n > 0，且為偶數): 10
2+4+...+10=30
```

## 程式碼

JPA03.java

```java
import java.util.Scanner;

public class JPA03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        
        // 用 do-while 迴圈取得使用者輸入的正偶數 n 
        
        int n = 0;
        
        do {
            System.out.print("請輸入 n 的值 (n > 0，且為偶數): ");
            n = keyboard.nextInt();
        } while ( !isPositiveEven(n) );
        
        // 用 do-while 迴圈將小於或等於 n 的正偶數加總
        
        int sum = 0, x = 2;
        
        do {
            sum += x;
            x += 2;
        } while ( x <= n );
        
        System.out.println("2+4+...+10=" + sum);
        
    }
    
    /**
     * 判斷是否為正偶數
     * 
     * @param n 數字參數
     * @return 如果數字是正偶數就回傳 true 否則傳回 false
     */
    static boolean isPositiveEven(int n) {
         return n > 0 && n % 2 == 0;
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        // 撰寫程式
    }
}```
