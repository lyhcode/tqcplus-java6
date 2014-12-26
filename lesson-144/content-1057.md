# 使用 Scanner 取得資料

Scanner 的使用範例如下：

    Scanner scanner = new Scanner(System.in);
    int num = scanner.nextInt();

請撰寫一程式，將使用者輸入的數字顯示在畫面，使用迴圈重複此程序，如果使用者輸入 0 就結束。

## 執行結果

```
Input: 99
=> 99
Input: 101
=> 101
Input: 123
=> 123
Input: 0

```

## 程式碼

Main.java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            System.out.print("Input: ");
            int num = scanner.nextInt();
            
            if (num == 0) {
                break;
            }
            
            System.out.println("=> " + num);
        }
    }
}

```

## 開始練習

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        //撰寫程式
    }
}
```
