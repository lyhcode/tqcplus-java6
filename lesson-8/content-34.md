# 308. 電腦週邊費用總計

1. David到某商場為公司購買一系列的電腦周邊設備，請以do-while計算此次購買的總費用，使「電腦費用周邊費用總計」程式正常執行。
2. do-while 的最大特點為：其內的 statement 至少會被執行一次。do-while 的語法如下:
    <pre>do {
        statement;
        ...
    } while (exp)</pre>
3. 請以 do-while 計算電腦周邊消費的總和。當使用者輸入-1，即停止執行並輸出結果。 
4. 答案顯示如下方Screen Dump輸出。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
請輸入消費金額，或輸入-1結束：20000
請輸入消費金額，或輸入-1結束：399
請輸入消費金額，或輸入-1結束：199
請輸入消費金額，或輸入-1結束：4000
請輸入消費金額，或輸入-1結束：2000
請輸入消費金額，或輸入-1結束：-1
電腦周邊總消費：26598
```

## 程式碼

JPA03.java

```java
import java.util.Scanner;

public class JPA03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        
        int total = 0, money = -1;
        
        do {            
            System.out.print("請輸入消費金額，或輸入-1結束：");
            money = keyboard.nextInt();
            
            if (money >= 0) {
                total += money;
            }
            
        } while (money != -1);
        
        System.out.println("電腦周邊總消費："+ total);
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD03 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String[] args) {
        ....
    }
}```
