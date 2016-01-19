# 306. 迴圈次方計算

1. 請設計一個程式持續輸入兩個數 m, n，m 與 n 中間以空格鍵分隔，並以一個類別方法及 while loop 計算 m 的 n 次方，直到輸入m=999為止。
2. 答案顯示如下方Screen Dump輸出。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
Input:
2 2
4
Input:
100 7
100000000000000
Input:
999
```

## 程式碼

JPA03.java

```java
import java.util.Scanner;

public class JPA03 {
	
	static Scanner keyboard = new Scanner(System.in);
	
    public static void main(String argv[]){
        int m = 0, n;
        
        while (m != 999) {
        	
        	System.out.println("Input:");
        	
        	m = keyboard.nextInt();
        	
        	if (m != 999) {
        		n = keyboard.nextInt();
        	
            	System.out.println(powerOf(m, n));
        	}
        }
    }  
  
    static long powerOf(int m, int n) {
        long result = 1;
        
        while (n >= 1) {
        	
        	result *= m;
        	
        	n--;
        }
        
        return result;
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD03 {
    
    static Scanner keyboard = new Scanner(System.in);
	
    public static void main(String argv[]){
        int m = 0, n;
        
        while (m != 999) {
        	
        	System.out.println("Input:");
        	
        	m = keyboard.nextInt();
        	
        	// ...
        }
    }  
  
    static long powerOf(int m, int n) {
        // ...
    }
}```
