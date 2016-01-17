# 109. 變數範圍

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 請依照右邊畫面所提供的程式，回傳正確值。 
2. gameRating 函數需呼叫 adder 方法以取得正確的加總值。 
3. adder 方法的計算方式為：skill + action + excitement。 
4. 輸出回傳的正確值，執行結果顯示如 Screen Dump。 


## 執行結果

```
The rating of the game is 23
```

## 程式碼

JPA01.java

```java
public class JPA01 {

    static int adder (int s, int a, int e) {
        return s + a + e;
    }

    static int gameRating (int s, int a, int e) {
        return adder(s, a, e);
    }

    public static void main(String argv[]) {
        int skill = 6, action = 9, excitment = 8;
        int result;
        
        result = gameRating(skill, action, excitment);
        
        System.out.print("The rating of the game is ");
        System.out.println(result);
    }
}
```

## 開始練習

```java
public class JPD01 {

    static int adder (_____, int a, _____) {
        return s + a + e;
    }

    static int gameRating (int s, int a, int e) {
        return adder(s, __, e);
    } 

    public static void main (String argv[]) {
        int skill = 6, action = 9, excitment = 8;
        int result;
        
        result = gameRating(skill, action, excitment);
        
        System.out.print("The rating of the game is ");
        System.out.println(result);
    }
}```
