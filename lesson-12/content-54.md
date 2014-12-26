# 502. 浮點數計算

1. 請撰寫一程式，由鍵盤輸入學生的人數，根據所輸入的學生人數，動態產生一個符合大小的浮點數陣列。
2. 將所輸入的每位學生成績存放到陣列裡(不限制輸入的小數點位數)。
3. 程式執行時，顯示【請輸入學生人數：】，要求輸入學生人數。
4. 接續要求輸入第1個至第n個學生的成績，n是剛才所輸入的學生人數。
5. 計算出人數、總分及平均值(不限制小數點位數)，顯示執行結果如 Screen Dump 畫面。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
請輸入學生人數：5
第1個學生的成績：81.24
第2個學生的成績：56.14
第3個學生的成績：92.84
第4個學生的成績：42.96
第5個學生的成績：64.37
人數：5
總分：337.55
平均：67.509995
```

## 程式碼

JPA05.java

```java
import java.util.Scanner;

public class JPA05 {
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String args[]) {
        System.out.print("請輸入學生人數：");
        int num = keyboard.nextInt();
        float[] score = new float[num];
        
        float sum = 0.0f;
        
        for (int i = 0; i < score.length; i++) {
            System.out.print("第" + (i + 1) + "個學生的成績：");
            score[i] = keyboard.nextFloat();
            sum += score[i];
        }
       
        System.out.println("人數：" + num + "\n總分：" + sum + "\n平均：" + (sum / num));
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD05 {
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String args[]) {
        System.out.print("請輸入學生人數：");

        //... 
    }
}```
