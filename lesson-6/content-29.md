# 208. 分級制度

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請寫出一個可以輸入學生分數，並判斷分數等級的程式。
2. 當分數 >= 90 分，等級為 A，【Your grade is A】。
3. 當分數介於 90 分到 80 分之間，例如 90 分 > 分數 >= 80 分，等級為 B，顯示【Your grade is B】。
4. 當分數介於 80 分到 70 分之間，例如 80 分 > 分數 >= 70 分，等級為 C，顯示【Your grade is C】。
5. 當分數介於 70 分到 60 分之間，例如 70 分 > 分數 >= 60 分，等級為 D，顯示【Your grade is D】。
6. 當分數小於 60 以下，例如 60 分 > 分數，等級為 F，顯示【Your grade is F】。
7. 程式執行時，畫面顯示【Input:】，請使用者輸入一個整數。
8. 重複執行五次，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Input:
    92
    Your grade is A
    Input:
    80
    Your grade is B
    Input:
    79
    Your grade is C
    Input:
    60
    Your grade is D
    Input:
    59
    Your grade is F

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input:
92
Your grade is A
Input:
80
Your grade is B
Input:
79
Your grade is C
Input:
60
Your grade is D
Input:
59
Your grade is F
```

## 程式碼

JPA02.java

```java
import java.util.*;

class JPA02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
        test();
        test();
        test();
    }
  
    public static void test() {
        int score;
        
        System.out.println("Input:");
        score = keyboard.nextInt();
        
        if (score >= 90) {
            System.out.println("Your grade is A");
        }
        else if (score >= 80) {
            System.out.println("Your grade is B");
        }
        else if (score >= 70) {
            System.out.println("Your grade is C");
        }
        else if (score >= 60) {
            System.out.println("Your grade is D");
        }
        else {
            System.out.println("Your grade is F");
        }
    }
}

```

## 開始練習

```java
import java.util.*;

class JPD02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
        test();
        test();
        test();
    }
  
    public static void test() {
        //撰寫程式
    }
}```
