# 506. 三維陣列元素之和

1. 設陣列 A 的維度為 4×2×3，試在程式碼裡宣告此一陣列，並在宣告同時設定初值，然後計算陣列 A 內所有元素的總和(SUM)。

        int A[4][2][3] =
            {{{1,2,3},{4,5,6}},
            {{7,8,9},{10,11,12}},
            {{13,14,15},{16,17,18}},
            {{19,20,21},{22,23,24}}};

2. 執行結果如Screen Dump所顯示。

難易度：易

程式及輸出全部正確使給分。

## 執行結果

```
sum = 300
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    public static void main(String[] argv) {
       int sum =0;
       int A[][][] = {{{1,2,3},{4,5,6}},
                       {{7,8,9},{10,11,12}},
                       {{13,14,15},{16,17,18}},
                       {{19,20,21},{22,23,24}}};
                               
       for(int i = 0; i < 4; i++)
          for(int j = 0; j < 2; j++)
             for(int k = 0; k < 3; k++)
                sum += A[i][j][k];
       
       System.out.printf("sum = %d\n", sum);
    }
}
```

## 開始練習

```java
public class JPD05 {
    public static void main(String[] argv) {
       int sum =0;
       int A[][][] = {{{1,2,3},{4,5,6}},
                       {{7,8,9},{10,11,12}},
                       {{13,14,15},{16,17,18}},
                       {{19,20,21},{22,23,24}}};
                               
       


       
       System.out.printf("sum = %d\n", sum);
    }
}```