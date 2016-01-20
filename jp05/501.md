# 501. 陣列計算

1. 請撰寫一程式，由鍵盤輸入 10 個整數，並存放到一陣列。
2. 程式執行時，顯示如 Screen Dump 的參考畫面，顯示【請輸入10個整數：】，並顯示【第1個整數：】，要求輸入第1個整數。
3. 依序要求輸入第1個至第10個整數，顯示執行結果如Screen Dump。
4. 判斷輸入 10 個整數後，計算陣列中大於 60 有幾個，這些大於 60 的數值總合及平均值，顯示如 Screen Dump。

## 執行結果

```
請輸入10個整數：
第1個整數：88
第2個整數：59
第3個整數：66
第4個整數：46
第5個整數：92
第6個整數：74
第7個整數：52
第8個整數：58
第9個整數：69
第10個整數：81
陣列中大於60的有6個
總合為470
平均值為78.33333333333333
```

## 程式碼

JPA05.java

```java
import java.util.Scanner;

public class JPA05 {
    public static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String args[]) {
        System.out.println("請輸入10個整數：");
        int[] data = new int[10];
        int sum = 0, n = 0;
        
        for (int i = 0; i < data.length; i++) {
            System.out.print("第" + (i + 1) + "個整數：");
            data[i] = keyboard.nextInt();
            if (data[i] > 60) {
                sum += data[i];
                n++;
            }
        }
        
        System.out.println("陣列中大於60的有" + n + "個\n總合為" + sum + "\n平均值為" + (sum / (double)n));
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD05 {

    public static void main(String args[]) {

        //...
        
        System.out.println("陣列中大於60的有" + n + "個\n總合為" + sum + "\n平均值為" + (sum / (double)n));
    }
}
```
