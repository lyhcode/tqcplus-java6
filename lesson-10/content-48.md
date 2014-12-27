# 406. 遞迴字串計算

1. 請使用遞迴撰寫一個類別方法，可計算一個字串內有幾個 A，大小寫有所區別。
2. 程式執行時，顯示【Input a string: 】要求輸入字串。
3. 連續執行兩次，結果參考Screen Dump，顯示【輸入的字串 has X As】。將計算此字串內有幾個 A，代入 X 中。

## 執行結果

```
Input a string: COMPUTER SKILLS FOUNDATION
COMPUTER SKILLS FOUNDATION has 1 As
Input a string: java 6
java 6 has 0 As
```

## 程式碼

JPA04.java

```java
import java.util.Scanner;

public class JPA04 {

    static Scanner scanner = new Scanner(System.in);

    public static void main(String args[]) {
        String input;
        
        input = prompt("Input a string: ");
        System.out.printf("%s has %d As\n", input, countA(input));
        
        input = prompt("Input a string: ");
        System.out.printf("%s has %d As\n", input, countA(input));
    }

    public static int countA(String str) {
        return count(str, "A");
    }
    
    public static int count(String str, String target) {
    	if (str.isEmpty()) {
            return 0;
        }
    	if (str.substring(0, 1).equals(target)) {
            return count(str.substring(1), target) + 1;
        }
    	return count(str.substring(1), target);
    }
    
    public static String prompt(String msg) {
    	System.out.println(msg);
    	return scanner.nextLine();
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
      System.out.print("Input a string: ");
      s = keyboard.nextLine();
      System.out.printf("%s has %d As\n", s, countA(s));
      System.out.print("Input a string: ");
      s = keyboard.nextLine();
      System.out.printf("%s has %d As\n", s, countA(s));
    }
    
    public static int countA(String str) {
          if (str.equals(____)) {
              return 0;
          } else if (str.substring(__, __).equals("A")) {
              return ______________________;
          } else {
              return countA(str.substring(1));
          }
      }
}```
