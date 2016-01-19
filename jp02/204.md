# 204. 公倍數計算

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請設計一程式，能判斷使用者所輸入的整數，是否能同時被5、9整除。 
2. 程式執行時，畫面顯示【Input:】，請使用者輸入一個整數。 
3. 計算是否能同時被 5 和 9 整除。 
4. 若此數字為 5 與 9 的公倍數，則印出【Yes】，否則印出【No】。 
5. 重複執行兩次，顯示如執行結果參考畫面。 

### 執行結果參考畫面 ###

    Input:
    90
    Yes
    Input:
    70
    No

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input:
90
Yes
Input:
70
No
```

## 程式碼

JPA02.java

```java
import java.util.*;

class JPA02 {
    static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
    }
  
    public static void test() {
        int num1;
    
        System.out.println("Input:");
        num1 = input.nextInt();
        if ((num1 % 5 == 0) && (num1 % 9 == 0)) {
            System.out.println("Yes");
        }
        else {
            System.out.println("No");
        }
    }
}

```

## 開始練習

```java
import java.util.*;

class JPD02 {
    static Scanner input = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
    }
  
    public static void test() {
        ...
    }
}
```
