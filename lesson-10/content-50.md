# 408. 遞迴字串反向

1. 護使用遞迴設計一個類別方法，此方法能夠將字串反向。
2. 程式執行時，顯示【Input a string: 】要求輸入字串。
3. 連續執行兩次，結果參考Screen Dump將字串反向印出。

教學用補充內容：

    reverse("car") = reverse("ar") + "c"

以下是這個程式執行過程的範例：

    reverse("car")
    =>return reverse("car".substring(1)) + "car".substring(0, 1);
    =>return reverse("ar") + "c";  
    =>return return reverse("ar".substring(1)) + "ar".substring(0, 1); + "c";
    =>return return reverse("r") + "a"; + "c";
    =>return return return "" + "r" + "a"; + "c";
    =>"rac"


## 執行結果

```
Input a string: computer
retupmoc
Input a string: skills
slliks
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
        System.out.printf("%s\n", reverse(s));
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.printf("%s\n", reverse(s));
    }
    
    public static String reverse(String str) {
        if (str.equals("")) {
            return "";
        } else {
            return reverse(str.substring(1)) + str.substring(0, 1);
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
        System.out.printf("%s\n", reverse(s));
        System.out.print("Input a string: ");
        s = keyboard.nextLine();
        System.out.printf("%s\n", reverse(s));
    }
    
    ...
}```
