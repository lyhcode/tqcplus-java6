# 使用 HashMap 與 For Each 處理資料

接續上一題，取得學生名字與分數，利用 HashMap 保存，利用 For Each 迴圈顯示全部資料，並將平均分數印出來。

註：名字輸入 ! 符號結束。

## 執行結果

```
Input Name: Jack
Input Score: 85
Jack => 85
Input Name: John
Input Score: 90
John => 90
Input Name: Mary
Input Score: 96
Mary => 96
Input Name: !
Jack: 85
Mary: 96
John: 90
Average: 90

```

## 程式碼

Main.java

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        Map<String, Integer> map = new HashMap<String, Integer>();
        
        while (true) {
            
            try {
                System.out.print("Input Name: ");
                String name = scanner.next();
                
                if (name.equals("!")) {
                    break;
                }
                
                System.out.print("Input Score: ");
                int num = scanner.nextInt();
                
                map.put(name, num);
                
                System.out.println(name + " => " + num);
            }
            catch (InputMismatchException ex) {
                System.out.println("Skip " + scanner.next());
            }
            
        }
        
        int sum = 0;
        
        for (String name: map.keySet()) {
            int score = map.get(name);
            sum += score;
            System.out.println(name + ": " + score);
        }
        
        System.out.println("Average: " + sum / map.size());
    }
}
```

## 開始練習

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        Map<String, Integer> map = /* 填空 */;
        
        while (true) {
            
            try {
                System.out.print("Input Name: ");
                String name = scanner.next();
                
                if (name.equals("!")) {
                    break;
                }
                
                System.out.print("Input Score: ");
                int num = scanner.nextInt();
                
                map.put(/* 填空 */);
                
                System.out.println(name + " => " + num);
            }
            catch (InputMismatchException ex) {
                System.out.println("Skip " + scanner.next());
            }
            
        }
        
        int sum = 0;
        
        for (/* 填空 */) {
            int score = /* 填空 */;
            sum += /* 填空 */;
            System.out.println(name + ": " + score);
        }
        
        System.out.println("Average: " + sum / /* 填空 */);
    }
}```
