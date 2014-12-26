# for-loop 實作練習 (2)

利用巢狀 for-loop 迴圈，印出以下「*」符號組成的圖形。

    *
    **
    ***
    ****
    *****

## 執行結果

```
*
**
***
****
*****

```

## 程式碼

Main.java

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j <= i; j++) {
                 System.out.print("*");
            }
            System.out.println("");
        }
    }
}

```

## 開始練習

```java
public class Main {
    public static void main(String[] args) {
        for (/*_______________*/) {
            for (/*_______________*/) {
                 System.out.print("*");
            }
            System.out.println("");
        }
    }
}
```
