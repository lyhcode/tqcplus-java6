# 307. 迴圈最大公因數

1. 請設計一個程式持續輸入兩個數 m, n，m 與 n 中間以斷行分隔，並以一個類別方法及 while loop 計算 m 與 n 最大公因數，直到輸入m=999為止。
2. 持續輸入兩個數 m、n，答案顯示如下方Screen Dump輸出的最大公因數。

中：程式及輸出全部正確使給分。

## 執行結果

```
Input:
8
12
4
Input:
13
19
1
Input:
7
49
7
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
        	
            	System.out.println(GCD(m, n));
        	}
        }
    }  
    
    /**
     * m = 27, n = 18
     * 27 % 18 = ... 9
     * m = 18, n = 9
     * 18 % 9 = ... 0
     * GCD(27, 18) = 9
     * m = 9, n = 0
     * found n = 0, return m (= 9)
     */
    static int GCD(int m, int n) {
    	int result = 1;
    	
    	while (n != 0){
            result = m % n;
            m = n;
            n = result;
        }
    	
    	return m;
    }
}
```

## 開始練習

```java
public class JPD03 {
    public static void main(String[] args) {
        //write here
    }
}```
