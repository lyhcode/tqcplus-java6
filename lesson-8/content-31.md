# 302. 巢狀迴圈

### 題目說明 ###

請修改 JPD03 程式碼，依下列題意完成作答。請注意，必須先將類別名稱 JPD03 修改為 JPA03 才能通過編譯。

### 設計說明 ###

1. 一個外迴圈包住一個或多個內迴圈的巢狀迴圈，每次執行外迴圈時，都會進入內迴圈，重複執行。
2. **「假設」**外迴圈重複了3次，而內迴圈重複了9次，則內迴圈內的敘述就會執行 3 * 9 次。
3. 那麼要如何修改程式碼，會使該程式的執行結果為27？
4. 顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    count = 27

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
count = 27
```

## 程式碼

JPA03.java

```java
public class JPA03 {
    
    public static void main(String[] args) {
        
        // 宣告變數
        int count = 0;
        
        // 第一個迴圈，i從1到3
        for (int i = 1; i <= 3; i++) {
            
            // 第二個迴圈，j從1到9
            for (int j = 1; j <= 9; j++) {
                // 當i等於1時，j會從1跑到9，
                // 當i等於2時，j也會從1跑到9。
                count++;
            }
        }
        
        System.out.printf("count = %d\n", count);
    }
}
```

## 開始練習

```java
public class JPD03 {
    
    public static void main(String[] args) {
        
        // 宣告變數
        //...
        
        // 第一個迴圈，i從1到3
        for (int i = 1; i <= 3; i++) {
            // 第二個迴圈，j從1到9
            //...
        }
        
        System.out.printf("count = %d\n", count);
    }
}```
