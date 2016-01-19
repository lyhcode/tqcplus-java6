# 509. 選擇排序法

1. 請使用選擇排序法(Selection Sort)撰寫程式。
2. 程式內有一資料陣列{1, 3, 2, 5, 4, 6}。
3. 請輸出選擇排序法的比對過程。
4. 執行結果如Screen Dump所顯示。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
 1 3 2 5 4 6
 1 2 3 5 4 6
 1 2 3 5 4 6
 1 2 3 4 5 6
 1 2 3 4 5 6
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
        int[] data = {1, 3, 2, 5, 4, 6};
        
        sort(data);
    }
    
    public static void sort(int[] data) {
        for (int i = 0; i < data.length - 1; i++) {
            // find minimun in i ~ data.length - 1
            int min = i;
            for (int j = i + 1; j < data.length; j++) {
                if (data[min] > data[j]) {
                    min = j;
                }
            }
            // swap data[i] with data[min]
            int tmp = data[i];
            data[i] = data[min];
            data[min] = tmp;
            
            for(int k:data)
                System.out.print(" " + k);
                
            System.out.println("");
        }
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
        int[] data = {1, 3, 2, 5, 4, 6};
        
        sort(data);
    }
    
    ...
}```
