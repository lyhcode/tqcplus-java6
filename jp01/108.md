# 108. 覆載方法

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 請在同一個類別中，使用覆載 (OverLoad) 撰寫三個同樣名為 add 的方法。
2. 宣告 main 方法，分別提供以下 a、b、c 等參數。
    * add(2, 3);
    * add(5.2, 4.3);
    * add("I love", "Java!!");
3. 方法一：傳入兩個整數 (int, int)，計算兩整數的和 (int)。程式執行時，列出【Adding two integers: i, j】，請呼叫 main 方法中的 add(2, 3)，將參數代入 i, j 內。
4. 方法二：傳入兩個浮點數 (double, double)，計算兩個浮點數的和 (double)，程式執行時，列出【Adding two double: i, j】，請呼叫 main 方法中的 add(5.2, 4.3)，將參數代入 i, j 內。 
5. 方法三：傳入兩字串 (String, String)，計算合併後的兩個字串 (String)，程式執行時，列出【Adding two string: i, j】，請呼叫 main 方法中的 add("I love", " Java!!")，將參數代入 i, j 內。 
6. 最後依序顯示此方個方法所計算出的列印值，執行結果顯示如 Screen Dump。 

### 執行結果參考畫面 ###

    Adding two integers: 2, 3
    Adding two doubles: 5.2, 4.3
    Adding two strings: I love,  Java!!
    5 9.500000 I love Java!!

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Adding two integers: 2, 3
Adding two doubles: 5.2, 4.3
Adding two strings: I love,  Java!!
5 9.500000 I love Java!!
```

## 程式碼

JPA01.java

```java
public class JPA01 {

    static int add(int i, int j) {
        System.out.println("Adding two integers: " + i + ", " + j);
        return i + j;
    }
    
    static double add(double i, double j) {
        System.out.println("Adding two doubles: "+ i + ", " + j);
        return i + j;
    }
    
    static String add(String i, String j) {
        System.out.println("Adding two strings: " + i + ", " + j);
        return i + j;
    }
    
    public static void main (String[] args) {
        int i = add(2, 3);
        double d = add(5.2, 4.3);
        String s = add("I love", " Java!!");
        System.out.printf("%d %f %s\n", i, d, s);
    }
}
```

## 開始練習

```java
public class JPD01 {
    
    //撰寫程式
        
    public static void main (String[] args) {
        int i = add(2, 3);
        double d = add(5.2, 4.3);
        String s = add("I love", " Java!!");
        System.out.printf("%d %f %s\n", i, d, s);
    }
}```
