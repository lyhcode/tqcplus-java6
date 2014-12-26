# 206. 及格分數

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請撰寫一個能輸入國文、英文、數學三科分數的程式。 
2. 程式執行時，如執行結果參考畫面(1)，畫面顯示【Input Chinese score:】，請使用者輸入國文分數，再分別依序要求輸入英文、數學的分數。 
3. 將此三個分數分別存入變數之中，再判斷是否有任何一科不及格，如果任何一科不及格，則輸出該科不及格，分別顯示【科目 failed.】；如果全部都及格則輸出全部通過，顯示【All Pass.】。 
4. 重複執行四次，顯示如執行結果參考畫面(2)。 

### 執行結果參考畫面 ###

(1) 程式執行時，畫面顯示【Input Chinese score:】，請使用者輸入國文分數。

    Input Chinese score:

(2) 分別依序要求輸入英文、數學的分數，判斷所輸入的成績是否及格。

    Input Chinese score:80
    Input English score:98
    Input Math score:55
    Math failed.
    Input Chinese score:10
    Input English score:80
    Input Math score:70
    Chinese failed.
    Input Chinese score:100
    Input English score:100
    Input Math score:100
    All pass.
    Input Chinese score:10
    Input English score:10
    Input Math score:10
    Chinese failed.
    English failed.
    Math failed.


### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input Chinese score:80
Input English score:98
Input Math score:55
Math failed.
Input Chinese score:10
Input English score:80
Input Math score:70
Chinese failed.
Input Chinese score:100
Input English score:100
Input Math score:100
All pass.
Input Chinese score:10
Input English score:10
Input Math score:10
Chinese failed.
English failed.
Math failed.
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
        test();
        test();
    }
    
    static void test() {
        int chi, eng, math;
        
        System.out.print("Input Chinese score:");
        chi = keyboard.nextInt();
        
        System.out.print("Input English score:");
        eng = keyboard.nextInt();
        
        System.out.print("Input Math score:");
        math = keyboard.nextInt();
        
        if ((chi >= 60) && (eng >= 60) && (math >= 60)) {
            
            System.out.println("All pass.");
            
        } else {
            if (chi < 60) {
                System.out.println("Chinese failed.");
            }
            
            if (eng < 60) {
                System.out.println("English failed.");
            }
            
            if (math < 60) {
                System.out.println("Math failed.");
            }
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
        test();
        test();
    }
    
    static void test() {
        int chi, eng, math;
        
        System.out.print("Input Chinese score:");
        chi = keyboard.nextInt();
        
        System.out.print("Input English score:");
        eng = keyboard.nextInt();
        
        System.out.print("Input Math score:");
        math = keyboard.nextInt();
        
        //撰寫程式
    }
}```
