# 505. 反轉陣列

1. 程式內有一陣列{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J"}。
2. 請用陣列方式寫出反轉陣列的程式，顯示{"J", "I", "H", "G", "F", "E", "D", "C", "B", "A"}。
3. 執行結果如Screen Dump。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
反轉陣列資料之前： A B C D E F G H I J
反轉陣列資料之後： J I H G F E D C B A
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
        String[] data = {"A", "B", "C", "D", "E", "F", "G", "H", "I", "J"};
        System.out.print("反轉陣列資料之前： ");
        for (int i = 0; i < data.length; i++) {
            System.out.print(data[i] + " ");
        }
        System.out.println();
        
        reverse(data);
        
        System.out.print("反轉陣列資料之後： ");
        for (int i = 0; i < data.length; i++) {
            System.out.print(data[i] + " ");
        }
        System.out.println();
    }
    
    public static void reverse(String[] data) {
        String tmp;
        for (int i = 0, j = data.length - 1; i < j; i++, j--) {
            tmp = data[i];
            data[i] = data[j];
            data[j] = tmp;
        }
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
        String[] data = {"A", "B", "C", "D", "E", "F", "G", "H", "I", "J"};
        System.out.print("反轉陣列資料之前： ");
        
        ...
        
        reverse(data);
        
        System.out.print("反轉陣列資料之後： ");
        
        ...
    }
    
    public static void reverse(__________) {
        ...
    }
}
```
