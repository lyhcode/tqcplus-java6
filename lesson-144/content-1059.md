# 使用 ArrayList 與 For Each 迴圈

接續上一題，請將輸入的資料放入 ArrayList 保存，並利用 For Each 迴圈顯示。

## 執行結果

```
Input: 98
=> 98
Input: 65
=> 65
Input: 79
=> 79
Input: 0
1: 98
2: 65
3: 79

```

## 程式碼

Main.java

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        List<Integer> list = new ArrayList<Integer>();
        
        while (true) {
            
            try {
                System.out.print("Input: ");
                int num = scanner.nextInt();
                
                if (num == 0) {
                    break;
                }
                
                list.add(num);
                
                System.out.println("=> " + num);
            }
            catch (InputMismatchException ex) {
                System.out.println("Skip " + scanner.next());
            }
            
        }
        
        int i = 0;
        
        for (int c : list) {
            System.out.println(++i + ": " + c);
        }
    }
}
```

## 開始練習

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        List<Integer> list = /* 填空 */;
        
        while (true) {
            
            try {
                System.out.print("Input: ");
                int num = scanner.nextInt();
                
                if (num == 0) {
                    break;
                }
                
                list.add(/* 填空 */);
                
                System.out.println("=> " + num);
            }
            catch (InputMismatchException ex) {
                System.out.println("Skip " + scanner.next());
            }
            
        }
        
        int i = 0;
        
        for (/* 填空 */) {
            System.out.println(++i + ": " + c);
        }
    }
}```
