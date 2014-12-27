# 504. 費氏數

1. 費氏數(Fibonacci sequence)可使用於建築設計，費氏數列為0、1、1、2、3、5、8、13、21、34、55、...，第一個數為0，第二個數為1，其它的數為前面兩個數的和。
2. 請用陣列方式寫出費氏數0、1、1、2、3、5、8、13、21、34 的程式。
3. 請事先宣告一個大小為10個整數陣列，將最前面二個陣列指定費氏數的初始值，並利用初始值來計算其餘的費氏數。
4. 以分行方式，顯示此費氏數的前10個數值如Screen Dump。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
0
1
1
2
3
5
8
13
21
34
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
    	
        int[] data = new int[10];

        data[0] = 0;
        data[1] = 1;

        for (int i = 2; i < data.length; i++) {
            data[i] = data[i-1] + data[i-2];
        }

        for (int i = 0; i < data.length; i++) {
            System.out.println(data[i]);
        }
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
        //...
    }
}
```
