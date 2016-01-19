# 510. 二分搜尋法

1. 程式內有已排序資料{5, 9, 13, 15, 17, 19, 25, 30, 45}，請使用二分搜尋法尋找輸入的資料。
2. 程式連續執行兩次，於程式執行時，如Screen Dump所示，顯示【請輸入要找尋的資料：】要求輸入欲尋找的資料n。
3. 若沒有搜尋到相符的數值，顯示【n不在陣列中】，將欲尋找的資料代入n，如Screen Dump所示。
4. 尋找時，列出尋找區間及此區間的中間值，搜尋幾次就列出幾項，最後產出【經過 y 次的尋找】，y代入搜尋次數；若有搜尋到相符的數值，值位在陣列中的第幾個位置，如Screen Dump所示。

難易度：難

程式及輸出全部正確使給分。

## 執行結果

```
請輸入要找尋的資料：2
尋找區間：0(5)..8(45),中間：4(17)
尋找區間：0(5)..3(15),中間：1(9)
尋找區間：0(5)..0(5),中間：0(5)
經過 3 次的尋找
2不在陣列中
請輸入要找尋的資料：30
尋找區間：0(5)..8(45),中間：4(17)
尋找區間：5(19)..8(45),中間：6(25)
尋找區間：7(30)..8(45),中間：7(30)
經過 3 次的尋找
您要找的資料在陣列中的第7個位置
```

## 程式碼

JPA05.java

```java
import java.util.Scanner;

public class JPA05 {
    public static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] argv) {
        search();
        search();
    }
    
    public static void search() {
        int[] data = {5, 9, 13, 15, 17, 19, 25, 30, 45}; // 已排序資料

        System.out.print("請輸入要找尋的資料：");

        int target = keyboard.nextInt();
    
        int high = data.length - 1; // 範圍區間右邊位置
        int low = 0; // 範圍區間左邊位置
        int middle = 0;
        int times = 0; // 搜尋次數

        while (low <= high) { // 還沒找完
            times++; // 累計次數
            middle = (low + high) / 2; // 找出中間值
    
            System.out.println("尋找區間：" + low + "(" + data[low] + ").." + high + "(" + data[high] + "),中間：" + middle + "(" + data[middle] + ")");
    
            if (target == data[middle]) // 找到了
                break;
            else if (target < data[middle]) // 在左半邊
                high = middle - 1;
            else // 在右半邊
                low = middle + 1;
        }

        System.out.println("經過 " + times + " 次的尋找");

        if (target == data[middle]) {
            System.out.println("您要找的資料在陣列中的第" +
            middle + "個位置");
        }
        else
            System.out.println(target + "不在陣列中");
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD05 {
    public static Scanner keyboard = new Scanner(System.in);
    
    public static void main(String[] argv) {
        search();
        search();
    }
    
    public static void search() {
        int[] data = {5, 9, 13, 15, 17, 19, 25, 30, 45}; // 已排序資料

        System.out.print("請輸入要找尋的資料：");

        int target = keyboard.nextInt();
    
        ...
    }
}```
