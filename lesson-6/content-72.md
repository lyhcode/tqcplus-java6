# 205. 倍數判斷

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請設計一程式，能判斷使用者所輸入的整數，是否為 2、3、6 的倍數。
2. 程式執行時，畫面顯示【Enter an integer:】，請使用者輸入一個整數。
3. 若輸入的整數是 2、3、6 的倍數，請輸出此整數是 2、3、6 哪些整數的倍數。若輸入的整數都不是 2、3、6 的倍數，請輸出【xx 不是 2、3、6 的倍數】，將使用者輸入的整數代入 xx 內。
4. 重複執行四次，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Enter an integer:
    30
    30是2、3、6的倍數
    Enter an integer:
    2
    2是2的倍數
    Enter an integer:
    9
    9是3的倍數
    Enter an integer:
    77
    77不是2、3、6的倍數

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Enter an integer:
30
30是2、3、6的倍數
Enter an integer:
2
2是2的倍數
Enter an integer:
9
9是3的倍數
Enter an integer:
77
77不是2、3、6的倍數
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
        int num;
        
        System.out.println("Enter an integer:");
        num = keyboard.nextInt();
        
        if (num % 2 == 0 && num % 3 == 0) {
            System.out.println(num + "是2、3、6的倍數");
        }
        else if (num % 2 == 0) {
            System.out.println(num + "是2的倍數");
        }
        else if (num % 3 == 0) {
            System.out.println(num + "是3的倍數");
        }
        else {
            System.out.println(num + "不是2、3、6的倍數");
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
        //撰寫程式
    }
}
```
