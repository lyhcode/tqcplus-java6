# For-each Loop

陣列使用 For-each 迴圈

    for (type var : arr) {
        body-of-loop
    }

相等 For 迴圈的寫法

    for (int i = 0; i < arr.length; i++) { 
        type var = arr[i];
        body-of-loop
    }

集合使用 For-each 迴圈

    for (type var : coll) {
        body-of-loop
    }

相等的 For 迴圈寫法

    for (Iterator<type> iter = coll.iterator(); iter.hasNext(); ) {
        type var = iter.next();
        body-of-loop
    }

## 執行結果

```
arr[0] = 101
arr[1] = 102
arr[2] = 103
arr[3] = 104
arr[4] = 105
101
102
103
104
105
list[0] = 601
list[1] = 602
list[2] = 603
601
602
603

```

## 程式碼

Main.java

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int arr[] = {
            101, 102, 103, 104, 105
        };
        
        for (int i = 0; i < arr.length; i++) {
            System.out.println("arr["+i+"] = " + arr[i]);
        }
        
        for (int val : arr) {
            System.out.println(val);
        }
        
        List<Integer> list = new ArrayList<Integer>();
        
        list.add(601);
        list.add(602);
        list.add(603);
        
        for (int i = 0; i < list.size(); i++) {
        	System.out.println("list["+i+"] = " + list.get(i));
        }
        
        for (Integer val : list) {
        	System.out.println(val);
        }
    }
}

```

## 開始練習

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int arr[] = {
            101, 102, 103, 104, 105
        };
        
        for (int i = 0; i < arr.length; i++) {
            System.out.println("arr["+i+"] = " + ____);
        }
        
        for (int val : arr) {
            System.out.println(____);
        }
        
        List<Integer> list = new ArrayList<Integer>();
        
        list.add(601);
        list.add(602);
        list.add(603);
        
        for (int i = 0; i < list.size(); i++) {
        	System.out.println("list["+i+"] = " + ____);
        }
        
        for (Integer val : list) {
        	System.out.println(____);
        }
    }
}
```
