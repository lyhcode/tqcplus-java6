# 508. 泡泡排序法

1. 請使用泡泡排序法(Bubble Sort)撰寫程式。
2. 程式內有一資料陣列{2, 4, 3, 5, 7, 6, 9, 1}。
3. 請輸出泡泡排序法的比對過程。
4. 執行結果如Screen Dump所顯示。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
 2 3 4 5 6 7 1
 2 3 4 5 6 1 7
 2 3 4 5 1 6 7
 2 3 4 1 5 6 7
 2 3 1 4 5 6 7
 2 1 3 4 5 6 7
 1 2 3 4 5 6 7
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
        int[] data = {2, 4, 3, 5, 7, 6, 9, 1};  // 為排序的資料
        int temp;  // 用來交換元素的暫存變數

        for (int i = 0; i < data.length - 1; i++) {
            // 共需進行元素個數-1輪
            for (int j = 0; j < data.length - 1 - i; j++) {
                // 第i輪比對到倒數第i+1個元素
                if(data[j] > data[j + 1]) {
                    temp = data[j];
                    data[j] = data[j + 1];
                    data[j + 1] = temp;
                }
            }

            for(int k = 0; k < data.length - 1; k++)
                System.out.print(" " + data[k]);
                
            System.out.println("");
        }
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
        int[] data = {2, 4, 3, 5, 7, 6, 9, 1};  // 為排序的資料
        ...
    }
}```
