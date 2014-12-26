# 202. 比較大小

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請設計一程式，使用者可以輸入兩個整數，並且可以比較兩個整數的大小。 
2. 程式執行時，畫面顯示【Input:】，請使用者輸入兩組整數，各組整數分別輸入兩個數字，數字中間以空隔鍵間隔。
3. 重複執行兩次，依輸入的兩個整數比較大小，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Input:
    50 88
    88 is larger than 50
    Input:
    33 45
    45 is larger than 33

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input:
50 88
88 is larger than 50
Input:
33 45
45 is larger than 33
```

## 程式碼

JPA02.java

```java
import java.util.*;

public class JPA02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
    }
    
    static void test() {
        int num1, num2;
        
        System.out.println("Input:");
        num1 = keyboard.nextInt();
        num2 = keyboard.nextInt();
        
        if (num1 > num2) {
            System.out.println(num1 + " is larger than " + num2);
        }
        else {
            System.out.println(num2+ " is larger than " + num1);
        }
    }
}

```

## 開始練習

```java
import java.util.*;

public class JPD02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
    }
    
    static void test() {
        //撰寫程式
    }
}```
