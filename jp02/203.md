# 203. 判斷奇偶數

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請設計一程式，使用者可輸入一個整數，判斷此整數為奇數或偶數。
2. 程式執行時，畫面顯示【Input an integer:】，請使用者輸入一個整數。
3. 重複執行兩次，如執行結果參考畫面。若為奇數，顯示【The number is odd.】；若為偶數，則顯示【The number is even.】。

### 執行結果參考畫面 ###

    Input an integer:
    7
    The number is odd.
    Input an integer:
    28
    The number is even.

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input an integer:
7
The number is odd.
Input an integer:
28
The number is even.
```

## 程式碼

JPA02.java

```java
import java.util.*;

public class JPA02 {
    static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
    }
    static void test() {
        int num;
        System.out.println("Input an integer:");
        num = input.nextInt();
        if (num % 2 == 0) {
            System.out.println("The number is even.");
        } else {
            System.out.println("The number is odd.");
        }
    }
}
```

## 開始練習

```java
import java.util.*;

public class JPD02 {
    static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
    }
    
    static void test() {
        ...
    }
}
```
