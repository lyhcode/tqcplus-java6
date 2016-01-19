# 409. 遞迴字串移除

1. 請使用遞迴撰寫一個類別方法，此方法能夠將一個字串內的某個字元移除。
2. 程式執行時，顯示【Input a string: 】要求輸入字串。
3. 輸入完畢，顯示【Input a character: 】要求輸入「欲移除」的字元。
4. 連續執行兩次，結果參考Screen Dump，將字元從字串中移除。

## 執行結果

```
Input a string: java se6
Input a character: a
jv se6
Input a string: computer
Input a character: p
comuter
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String args[]) {
        String s, c; 
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c = keyboard.nextLine();
        System.out.printf("%s\n", removeChar(s, c));
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c = keyboard.nextLine();
        System.out.printf("%s\n", removeChar(s, c));
    }
    
    public static String removeChar(String str, String c) {
        if (str.equals("")) {
              return "";
        } else if (str.substring(0, 1).equals(c)) {
            return removeChar(str.substring(1), c);
        } else {
            return str.substring(0, 1) + removeChar(str.substring(1), c);
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
        String s, c; 
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c = keyboard.nextLine();
        System.out.printf("%s\n", removeChar(s, c));
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.print("Input a character: ");
        c = keyboard.nextLine();
        System.out.printf("%s\n", removeChar(s, c));
    }
    
    ...
}```
