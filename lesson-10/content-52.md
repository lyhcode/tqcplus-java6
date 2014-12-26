# 410. 遞迴字串替換

1. 請使用遞迴撰寫一個類別方法，此方法能夠將一個字串內的某個字元換成另一個字元。例如輸入字串【windows】，將字串中 w 值替換成 g 值，輸出字串為【gindogs】。
2. 程式執行時，顯示【Input a string: 】要求輸入字串，接續顯示【Input a character: 】要求輸入「被替換」的字元，最後顯示【Input another character: 】要求輸入替換字元。
3. 請利用 replace()函數進行字串替換，顯示結果參考Screen Dump。

## 執行結果

```
Input a string: windows
Input a character: w
Input another character: g
gindogs
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        String s, c1, c2; 
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c1 = keyboard.nextLine();
        System.out.print("Input another character: ");
        c2 = keyboard.nextLine();
        System.out.printf("%s\n", replace(s, c1, c2));
    }
    
    public static String replace(String str, String c1, String c2) {
        if (str.equals("")) {
              return "";
        } else if (str.substring(0, 1).equals(c1)) {
            return c2 + replace(str.substring(1), c1, c2);
        } else {
            return str.substring(0, 1) + replace(str.substring(1), c1, c2);
        }
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        String s, c1, c2; 
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c1 = keyboard.nextLine();
        System.out.print("Input another character: ");
        c2 = keyboard.nextLine();
        System.out.printf("%s\n", replace(s, c1, c2));
    }
    
    ...
}```
