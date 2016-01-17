# 104. 距離計算

難易度：中

## 題目說明

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

## 設計說明

1. Math 套件（package）內有許多數學上常用的函數。
2. 請使用 Math.pow 及 Math.sqrt 撰寫程式，顯示【輸入第1組的 x 和 y 座標：】，提示使用者首先輸入第一組座標(x1, y1)，x 與 y 座標的輸入以一空格鍵分隔，其資料型態皆為正整數。
3. 要求輸入第 2 組座標(x2, y2)。
4. 兩組座標輸入完畢，輸出兩組座標之間的距離，顯示如執行結果參考「標準輸出」。

## 執行流程

1. 提示使用者首先輸入第一組座標 (x1: 1, y1: 5)
2. 要求輸入第二組座標 (x2: 10, y2: 22)
3. 兩組座標輸入完畢，輸出兩組座標之間的距離。

## 執行結果

```
輸入第1組的x和y座標：1 5
輸入第2組的x和y座標：10 22
介於(1.00,5.00)和(10.00,22.00)之間的距離是19.24。
```

## 評分項目

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 程式碼

JPA01.java

```java
import java.util.Scanner;

public class JPA01 {
    public static void main(String args[]) {
        double x1, y1, x2, y2, distance;
        Scanner keyboard = new Scanner(System.in);
        
        System.out.print("輸入第1組的x和y座標：");
        x1 = keyboard.nextDouble();
        y1 = keyboard.nextDouble();
        
        System.out.print("輸入第2組的x和y座標：");
        x2 = keyboard.nextDouble();
        y2 = keyboard.nextDouble();
        distance = Math.sqrt(Math.pow(x1 - x2, 2) + Math.pow(y1 - y2, 2));
        
        System.out.printf("介於(%.2f,%.2f)和(%.2f,%.2f)之間的距離是%.2f。\n",x1, y1, x2, y2, distance);
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD01 {
    public static void main(String args[]) {
        double x1, y1, x2, y2, distance;
        Scanner keyboard = ______________________;
        
        System.out.print("輸入第1組的x和y座標：");
        x1 = keyboard.nextDouble();
        y1 = keyboard.nextDouble();
        
        System.out.print("輸入第2組的x和y座標：");
        ___________________________
        ___________________________
        distance = Math.sqrt(Math.pow(x1 - x2, 2) + Math.pow(y1 - y2, 2));
        
        System.out.printf("介於(____,____)和(%.2f,%.2f)之間的距離是_____。\n",x1, y1, x2, y2, __________);
    }
}```
