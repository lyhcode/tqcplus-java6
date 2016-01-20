# 303. 完美數

### 題目說明 ###

請修改 JPD03 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD03 修改為 JPA03 才能通過編譯。

### 設計說明 ###

1. 一個數如果恰好等於它的因數（不含數字本身）之和，這個數就稱為「完美數」。
2. 例如 6 = 1 + 2 + 3，因 1、2與3都是6的因數，因而6是完美數。
3. 試設計一程式，找出1000以內的所有完美數。
4. 顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    1~1000中的完美數有: 6 28 496

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
1~1000中的完美數有: 6 28 496

```

## 程式碼

JPA03.java

```java
public class JPA03 {

    public static void main(String[] args) {

        System.out.printf("1~1000中的完美數有:");

        // 使用 FOR 迴圈
        for (int num = 2; num <= 1000; num++) {
            
            int sum = 0;
            
            // 找出因數，並累加
            for (int i = 1; i < num; i++) {
                if (num % i == 0) {
                    sum += i;
                }
            }
            
            if (sum == num) {
                System.out.print(" " + num);
            }
        }
        
        System.out.println("");
    }
}
```

## 開始練習

```java
public class JPD03 {
    
    public static void main(String[] args) {
        // 使用 FOR 迴圈
        //...
    }
}```
