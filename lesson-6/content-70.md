# 201. 分數篩選

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請設計一程式，此程式能判斷輸入分數是否及格，程式執行時，顯示【Please enter score:】要求輸入分數。
2. 如果使用者輸入的分數大於等於60，則輸出【You pass】。
3. 如果使用者的分數小於60，則不做任何處裡。
4. 最後由電腦輸出【End】代表程式結束。
5. 重複執行兩次，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Please enter score:
    98
    You pass
    End
    Please enter score:
    45
    End

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Please enter score:
98
You pass
End
Please enter score:
45
End
```

## 程式碼

JPA02.java

```java
import java.util.Scanner;

public class JPA02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
    }
    
    static void test() {
        
        int score;
        
        System.out.println("Please enter score:");
        score = keyboard.nextInt();
        
        if (score >= 60) {
            //分數判斷結果為及格
            System.out.println("You pass");
        }
        
        System.out.println("End");
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD02 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        test();
        test();
    }
    
    static void test() {
        //撰寫程式
    }
}
```
