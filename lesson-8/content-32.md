# 304. 餐點費用

### 題目說明 ###

請修改 JPD03 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD03 修改為 JPA03 才能通過編譯。

### 設計說明 ###

1. 有五位朋友到知名美式餐廳聚餐慶生，此餐廳採點餐的計算方式。
2. 程式執行時，如執行結果參考畫面，畫面顯示【Please enter meal dollars or enter -1 to stop:】，請使用者輸入第一道餐點費用，再分別依序要求輸入其他道餐點的費用。
3. 若要停止執行程式計算，需輸入-1後停止程式計算，-1不列入餐點計算費用內。如執行結果參考畫面，輸出餐點數量、所有餐點的總費用及平均負擔費用，平均值取自小數第二位。
4. 顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    Please enter meal dollars or enter -1 to stop: 180
    Please enter meal dollars or enter -1 to stop: 120
    Please enter meal dollars or enter -1 to stop: 99
    Please enter meal dollars or enter -1 to stop: 399
    Please enter meal dollars or enter -1 to stop: 150
    Please enter meal dollars or enter -1 to stop: -1
    餐點總費用:948
    5 道餐點平均費用為: 189.60

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
Please enter meal dollars or enter -1 to stop: 180
Please enter meal dollars or enter -1 to stop: 120
Please enter meal dollars or enter -1 to stop: 99
Please enter meal dollars or enter -1 to stop: 399
Please enter meal dollars or enter -1 to stop: 150
Please enter meal dollars or enter -1 to stop: -1
餐點總費用: 948
5 道餐點平均費用為: 189.60
```

## 程式碼

JPA03.java

```java
import java.util.Scanner;

public class JPA03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    // 設定終止計算的條件
    static int stop = -1;
    
    public static void main(String[] args) {
        
        // 宣告變數
        int total = 0;
        int dollar = 0;
        int count = 0;
        
        // 使用 WHILE 迴圈
        while (dollar != stop) {
            System.out.print("Please enter meal dollars or enter -1 to stop: ");
            dollar = keyboard.nextInt();

            if (dollar != stop) {
                 total += dollar;
                 count++;
            }
        }
        
        System.out.println("餐點總費用: " + total);
        System.out.printf("%d 道餐點平均費用為: %.2f\n", count, (double)total/count);
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD03 {
    
    static Scanner keyboard = new Scanner(System.in);
    
    // 設定終止計算的條件
    static int stop = -1;
    
    public static void main(String[] args) {
        
        // 宣告變數
        int total = 0;
        int dollar = 0;
        int count = 0;
        
        // 使用 WHILE 迴圈
        while (dollar != stop) {
            // 撰寫程式碼
            //...
        }
        
        System.out.println("餐點總費用: " + total);
        System.out.printf("%d 道餐點平均費用為: %.2f\n", count, (double)total/count);
    }
}```
