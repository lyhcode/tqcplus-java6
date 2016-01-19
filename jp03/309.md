# 309. 迴圈倍數判斷

1. 如下為 continue 之範例寫法（請參考 Sample 程式碼）。
2. 請使用 continue 設計一個程式，能夠計算1到「使用者輸入的數」之中，哪些數是3的倍數或是5的倍數，
而不是7的倍數。
3. 將這些數相加後，答案顯示如下方Screen Dump輸出。


中：程式及輸出全部正確使給分。

    class Sample {
        public static void main(String argv[]) throws IOException {
            for (int i = 0; i < 5; i++) {
                if (i == 2) {
                    continue;
                }
                System.out.println("i = " + i);
            }
        }
    }

    Output：
    i = 0
    i = 1
    i = 3
    i = 4

## 執行結果

```
9
Answer: 23
```

## 程式碼

JPA03.java

```java
import java.util.*;

public class JPA03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] args) {
        int num;
        int sum = 0;
        
        num = keyboard.nextInt();
        
        for (int i = 0; i <= num; i++) {
            if (i % 7 == 0) {
                continue;
            }
            if (i % 3 == 0 || i % 5 == 0) {
                sum += i;
            }
        }
        
        System.out.println("Answer: " + sum);
    }
}
```

## 開始練習

```java
public class JPD03 {
    public static void main(String[] args) {
        // 撰寫程式
    }
}```
