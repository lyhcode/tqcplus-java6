# 301. 整數連加

### 題目說明 ###

請修改 JPD03 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD03 修改為 JPA03 才能通過編譯。

### 設計說明 ###

1. 請使用 for loop 寫一個程式，輸入一個正整數 N，計算 1 + 2 + 3 ... + N 的結果。
2. 程式執行時，顯示【Input:】要求輸入一正整數，輸入完畢，於下方計算 1 + ... + N 的總和。
3. 顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Input:
    88
    1 + ... + 88 = 3916

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input:
88
1 + ... + 88 = 3916
```

## 程式碼

JPA03.java

```java
import java.util.*;

public class JPA03 {
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String argv[]) {
        // 宣告變數
        int num;
        int sum = 0;
        
        // 取得鍵盤輸入資料
        System.out.println("Input:");
        num = keyboard.nextInt();
        
        // 迴圈內容
        for (int i = 1; i <= num; i++) {
            sum += i;                       
        }
        
        System.out.println("1 + ... + " + num + " = " + sum);
    }
}
```

## 開始練習

```java
import java.util.*;

public class JPD03 {
    public static void main(String argv[]) {
        // 宣告變數
        //...
        
        // 取得鍵盤輸入資料
        //...
        
        // 迴圈內容
        for (__________; __________; __________) {
            _____ = __________;                       
        }
        
        System.out.println(____________________);
    }
}
```
