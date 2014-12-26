# 使用 Exception 例外處理

接續上一題，請利用 try ... catch ... 語法，當使用者輸入的資料不是整數（int）時，顯示略過（skip）的訊息。

提示：使用 InputMismatchException 例外處理。

## 執行結果

```
Input: 101
=> 101
Input: 99
=> 99
Input: string
Skip string
Input: 123
=> 123
Input: 0

```

## 程式碼

Main.java

```java
import java.util.Scanner;
import java.util.InputMismatchException;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            
            try {
                System.out.print("Input: ");
                int num = scanner.nextInt();
                
                if (num == 0) {
                    break;
                }
                
                System.out.println("=> " + num);
            }
            catch (InputMismatchException ex) {
                System.out.println("Skip " + scanner.next());
            }
            
        }
    }
}
```

## 開始練習

```java
import java.util.Scanner;
import java.util.InputMismatchException;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            
            //撰寫程式
            
        }
    }
}```
