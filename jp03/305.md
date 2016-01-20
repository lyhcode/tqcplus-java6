# 305. 迴圈階乘計算

1. 請設計一程式計算 n 的階乘。
2. n 為使用者任意輸入的整數值，n 值範圍介於 1 到 10 之間。
3. 程式執行時，畫面顯示【Please enter one value:】，首先判斷 n 值是否介於1到10之間，若檢核通過，則輸出階乘計算後之數值；若沒有介於1至10之間，則顯示【Error, the value is out of range.】。
4. 重複執行三次，答案顯示如下方Screen Dump輸出。

中：程式及輸出全部正確使給分。

## 執行結果

```
Please enter one value: 0
Error, the value is out of range.
Please enter one value: 12
Error, the value is out of range.
Please enter one value: 6
6!: 720
```

## 程式碼

JPA03.java

```java
import java.util.Scanner;

public class JPA03 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
        test();
    }
    
    public static void test() {
        int i = 1, total = 1, n;
        System.out.print("Please enter one value: ");
        n = keyboard.nextInt();
        if ((n >= 1) && (n <= 10)) {
            while (i <= n) {
                total = total * i;
                i = i + 1;
            }
            System.out.println(n + "!: " + total);
        } else {
            System.out.println("Error, the value is out of range.");
        }
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD03 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
        test();
    }
    
    public static void test() {
        ...
    }
}
```
