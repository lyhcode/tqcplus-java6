# 209. 象限座標

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請撰寫程式，輸入 x、y 座標值，判斷該點位於何象限或是在哪個座標軸上。
2. 程式執行時，畫面顯示【請輸入 x 座標：】要求輸入 x 座標。
3. 重複執行四次，顯示如執行結果參考畫面。

※ 舉例：若輸入的座標值為 ``(3.0,-2.5)``，輸出【座標值+在第四象限】；若輸入的座標值為 ``(4.5,0.0)``，則輸出【座標值+在 x 軸上】。

### 執行結果參考畫面 ###

    請輸入x座標：4.5
    請輸入y座標：0.0
    (4.50,0.00)在x軸上
    請輸入x座標：0
    請輸入y座標：3.2
    (0.00,3.20)在y軸上
    請輸入x座標：-5.5
    請輸入y座標：-3.8
    (-5.50,-3.80)在第三象限
    請輸入x座標：-4.3
    請輸入y座標：7.2
    (-4.30,7.20)在第二象限

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
請輸入x座標：4.5
請輸入y座標：0.0
(4.50,0.00)在x軸上
請輸入x座標：0
請輸入y座標：3.2
(0.00,3.20)在y軸上
請輸入x座標：-5.5
請輸入y座標：-3.8
(-5.50,-3.80)在第三象限
請輸入x座標：-4.3
請輸入y座標：7.2
(-4.30,7.20)在第二象限
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
    
    public static void test() {
        double x, y;
        
        System.out.print("請輸入x座標：");
        x = keyboard.nextDouble();
        
        System.out.print("請輸入y座標：");
        y = keyboard.nextDouble();
        
        if (x == 0.0 && y == 0.0) {
            System.out.printf("(%.2f,%.2f)為原點\n", x, y);
        }
        else if (x == 0.0 && y != 0.0) {
            System.out.printf("(%.2f,%.2f)在y軸上\n", x, y);
        }
        else if (x != 0.0 && y == 0.0) {
            System.out.printf("(%.2f,%.2f)在x軸上\n", x, y);
        }
        else if (x > 0.0 && y > 0.0) {
            System.out.printf("(%.2f,%.2f)在第一象限\n", x, y);
        }
        else if (x < 0.0 && y > 0.0) {
            System.out.printf("(%.2f,%.2f)在第二象限\n", x, y);
        }
        else if (x < 0.0 && y < 0.0) {
            System.out.printf("(%.2f,%.2f)在第三象限\n", x, y);
        }
        else if (x > 0.0 && y < 0.0) {
            System.out.printf("(%.2f,%.2f)在第四象限\n", x, y);
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
    
    public static void test() {
        //撰寫程式
    }
}
```
