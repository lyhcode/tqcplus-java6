# 210. 鍵盤字元判斷

### 題目說明 ###

請修改 JPD02 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD02 修改為 JPA02 才能通過編譯。

### 設計說明 ###

1. 請使用 ``switch`` 完成編輯區中的 ``test()`` 的程式。
2. 程式執行時，畫面顯示【Input a character:】，請使用者輸入一個英文字母。
3. 若輸入 a 或 b ，顯示【You entered a or b】。
4. 若輸入 x ，顯示【You entered x】；若輸入 y，顯示【You entered y】。
5. 若皆非上述所列英文字母，則顯示【You entered something else.】。

### 執行結果參考畫面 ###

    Input a character:
    a
    You entered a or b
    Input a character:
    b
    You entered a or b
    Input a character:
    x
    You entered x
    Input a character:
    y
    You entered y
    Input a character:
    c
    You entered something else.

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Input a character:
a
You entered a or b
Input a character:
b
You entered a or b
Input a character:
x
You entered x
Input a character:
y
You entered y
Input a character:
c
You entered something else.
```

## 程式碼

JPA02.java

```java
import java.util.*;

class JPA02 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
        test();
        test();
        test();
    }
  
    public static void test() {
        String st;
        char c;
    
        System.out.println("Input a character:");
        st = keyboard.nextLine();
        c = st.charAt(0);
        switch (c) {
            case 'a':
            case 'b':
                  System.out.println("You entered a or b");
                  break;
            case 'x':
                  System.out.println("You entered x");
                  break;
            case 'y':
                  System.out.println("You entered y");
                  break;
            default:
                  System.out.println("You entered something else.");
        }
    }
}
```

## 開始練習

```java
import java.util.*;
class JPD02 {
    static Scanner keyboard = new Scanner(System.in);
    public static void main(String[] args) {
        test();
        test();
        test();
        test();
        test();
    }
  
    public static void test() {
        ...
    }
}```
