# 507. 停車費用計算

1. 請用陣列方式寫出停車費用計算的程式。
2. 假設停車時段分為：
   - 2小時以內(含2小時)，每小時以30元計算。
   - 2小時以上不足4小時，每小時以50元計算。
   - 4小時以上不足6小時，每小時以80元計算。
   - 6小時以上，每小時以100元計算。
3. 請輸入停車時數並計算出停車費用，分別計算2小時、3小時、5小時及8小時的應繳費用，顯示結果如Screen Dump。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
停車時數：2小時
應繳費用：60元整
--------------------
停車時數：3小時
應繳費用：110元整
--------------------
停車時數：5小時
應繳費用：240元整
--------------------
停車時數：8小時
應繳費用：520元整
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
        int hours = 0;   //停車時數

        hours = 2;
        park(hours);
        System.out.println("--------------------");
        
        hours = 3;
        park(hours);
        System.out.println("--------------------");
        
        hours = 5;
        park(hours);
        System.out.println("--------------------");
        
        hours = 8;
        park(hours);
    }
    
    public static void park(int hours) {
        int[] hourTable = {0, 2, 4, 6};   // 時段
        int[] feeTable = {30, 50, 80, 100};   // 時段費率
        int fee = 0;   //停車費用
        
        System.out.println("停車時數：" + hours + "小時");
        
        int i = hourTable.length - 1;
        while (i > 0) {   // 先找出最高費率區段
            if (hourTable[i] < hours)
                break;
            i--;
        }

        while (i >= 0) {   // 由最高費率區段往下累加
            fee += (hours - hourTable[i]) * feeTable[i];
            hours = hourTable[i];
            i--;
        }

        System.out.println("應繳費用：" + fee + "元整");
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
        int hours = 0;   //停車時數

        hours = 2;
        park(hours);
        System.out.println("--------------------");
        
        hours = 3;
        park(hours);
        System.out.println("--------------------");
        
        hours = 5;
        park(hours);
        System.out.println("--------------------");
        
        hours = 8;
        park(hours);
    }
    
    public static void park(int hours) {
        int[] hourTable = {0, 2, 4, 6};   // 時段
        int[] feeTable = {30, 50, 80, 100};   // 時段費率
        int fee = 0;   //停車費用
        
        ...

        System.out.println("應繳費用：" + fee + "元整");
    }
}```
