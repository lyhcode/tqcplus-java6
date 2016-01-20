# 407. 尾端遞迴計算總和

1. 請使用尾端遞迴及迴圈撰寫一個類別方法，此方法能夠計算一個數字字串內所有數字的和。
2. 程式執行時，顯示【Input a string of numbers: 】要求輸入數字字串。
3. 連續執行兩次，結果參考Screen Dump，列出以「尾端遞迴」及「迴圈」計算後之數字總和。

## 執行結果

```
Input a string of numbers: 1234
尾端遞迴：10
迴圈：10
Input a string of numbers: 3456
尾端遞迴：18
迴圈：18
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        String s; 
        System.out.print("Input a string of numbers: ");
        s = keyboard.nextLine();
        System.out.printf("尾端遞迴：%d\n", sumTail(s, 0));
        System.out.printf("迴圈：%d\n", sumLoop(s, 0));
        System.out.print("Input a string of numbers: ");
        s = keyboard.nextLine();
        System.out.printf("尾端遞迴：%d\n", sumTail(s, 0));
        System.out.printf("迴圈：%d\n", sumLoop(s, 0));
    }
    
    public static int sumTail(String str, int r) {
        if (str.equals("")) {
            return r;
        } else  {
            return  sumTail(str.substring(1), r + Integer.parseInt(str.substring(0, 1)));
        }
    }
    
    public static int sumLoop(String str, int r) {
        while (!str.equals("")) {
            r = r + Integer.parseInt(str.substring(0, 1));
            str = str.substring(1);
        }
        return r;
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        String s; 
        System.out.print("Input a string of numbers: ");
        s = keyboard.nextLine();
        System.out.printf("尾端遞迴：%d\n", sumTail(s, 0));
        System.out.printf("迴圈：%d\n", sumLoop(s, 0));
        System.out.print("Input a string of numbers: ");
        s = keyboard.nextLine();
        System.out.printf("尾端遞迴：%d\n", sumTail(s, 0));
        System.out.printf("迴圈：%d\n", sumLoop(s, 0));
    }
    
    
   ...

}```
