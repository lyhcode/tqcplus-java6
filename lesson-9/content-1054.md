# 遞迴實作練習 (1)

請設計 countDown 遞迴函式，傳遞一個數字作為參數，倒數至零並將每個階段的數字印出。

測試案例：

    countDown(5);

執行結果：

    5
    4
    3
    2
    1
    0
    END

## 執行結果

```
5
4
3
2
1
0
END
8
7
6
5
4
3
2
1
0
END

```

## 程式碼

Main.java

```java
public class Main {
    public static void main(String[] args) {
        countDown(5);
        countDown(8);
    }
    
    static void countDown(int n) {
        System.out.println(n);
        
        if (n > 0) {
             countDown(n - 1);
        }
        else {
             System.out.println("END");
        }
    }
}
```

## 開始練習

```java
public class Main {
    public static void main(String[] args) {
        countDown(5);
        countDown(8);
    }
    
    static void countDown(int n) {
          // 撰寫程式
    }
}```
