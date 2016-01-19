# 207. 三角形邊長判斷

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請寫一個判斷三角形的程式：當三個邊長能夠構成三角形時，再判斷該三角形為鈍角、銳角或是直角三角形，否則請顯示【不可以構成三角形】。
2. 構成三角形存在條件：任兩邊相加大於第三邊，且皆不可為 0。
3. 直角三角形：其中有兩個邊的平方和等於第三邊的平方。
4. 鈍角三角形：其中有兩個邊的平方和小於第三邊的平方。
5. 銳角三角形：任兩邊的平方和大於第三邊的平方。
6. 程式執行時，畫面顯示【請輸入三個整數：】要求輸入三邊的邊長。
7. 重複執行四次，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    請輸入三個整數：3 4 5
    直角三角形
    請輸入三個整數：3 4 6
    鈍角三角形
    請輸入三個整數：4 4 3
    銳角三角形
    請輸入三個整數：2 4 7
    不可以構成三角形

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
請輸入三個整數：3 4 5
直角三角形
請輸入三個整數：3 4 6
鈍角三角形
請輸入三個整數：4 4 3
銳角三角形
請輸入三個整數：2 4 7
不可以構成三角形
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
        int a, b, c;
        
        System.out.print("請輸入三個整數：");
        a = keyboard.nextInt();
        b = keyboard.nextInt();
        c = keyboard.nextInt();
        
        if ( (a+b>c) && (b+c>a) && (c+a>b) ) {
            if ( (a*a+b*b==c*c) || (b*b+c*c==a*a) || (c*c+a*a==b*b) ) {
                System.out.printf("直角三角形\n");
            }
            else if ( (a*a+b*b<c*c) || (b*b+c*c<a*a) || (c*c+a*a<b*b) ) {
                System.out.printf("鈍角三角形\n");
            }
            else {
                System.out.printf("銳角三角形\n");
            }
        } else {
            System.out.printf("不可以構成三角形\n");
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
