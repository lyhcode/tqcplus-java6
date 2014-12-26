# 遞迴實作練習 (3)

執行範例：

    recursive(10);

輸出訊息：

    10+9+8+7+6+5+4+3+2+1=55


## 執行結果

```
4+3+2+1=10
10+9+8+7+6+5+4+3+2+1=55

```

## 程式碼

Main.java

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("4+3+2+1="+recursive(4));
        System.out.println("10+9+8+7+6+5+4+3+2+1="+recursive(10));
    }
    
    static int recursive(int n) {
        if (n > 0) {
             return n + recursive(n-1);
        }
        return n;
    }
}

```

## 開始練習

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("4+3+2+1="+recursive(4));
        System.out.println("10+9+8+7+6+5+4+3+2+1="+recursive(10));
    }
    
    static int recursive(int n) {
        // 撰寫程式
    }
}
```
