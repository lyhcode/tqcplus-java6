# 503. 矩陣之和

1. 試撰寫一個函數，此函數可用來計算矩陣 A 與 B 的和，使「矩陣之和」程式正常執行。

        int A[][] = {{1, 2, 3}, {4, 5, 6}};
        int B[][] = {{7, 8, 9}, {10, 11, 12}};

2. 計算矩陣 A 與 B 的和，並把相加後的結果放在矩陣 C 裡。
3. 顯示執行結果如Screen Dump。

難易度：中

程式及輸出全部正確使給分。

## 執行結果

```
陣列A的內容為(2x3)：
01 02 03
04 05 06

陣列B的內容為(2x3)：
07 08 09
10 11 12

陣列A+B=C，陣列C的內容為(3x3)：
08 10 12
14 16 18
```

## 程式碼

JPA05.java

```java
public class JPA05 {
    final static int ROW = 2;
    final static int COL = 3;

    public static void main(String args[]) {
        int A[][] = {{1,2,3}, {4,5,6}};
        int B[][] = {{7,8,9}, {10,11,12}};
        int C[][] = new int[ROW][COL];
       
        System.out.printf("陣列A的內容為(2x3)：\n");   
        show(A);
       
        System.out.printf("\n陣列B的內容為(2x3)：\n");   
        show(B);
       
        add(A, B, C);
       
        System.out.printf("\n陣列A+B=C，陣列C的內容為(3x3)：\n");   
        show(C);
    }
    
    public static void add(int a[][], int b[][], int c[][]) {
        for(int i = 0; i < ROW; i++)
            for(int j = 0; j < COL; j++)
                c[i][j] = a[i][j] + b[i][j];
    }
    
    public static void show(int c[][]) {
        for(int i = 0; i < ROW; i++) {
            for(int j = 0; j < COL; j++)
                System.out.printf("%02d ", c[i][j]);

            System.out.printf("\n");
        }
    }
}
```

## 開始練習

```java
public class JPD05 {
    final static int ROW = 2;
    final static int COL = 3;

    public static void main(String args[]) {
        int A[][] = {{1,2,3}, {4,5,6}};
        int B[][] = {{7,8,9}, {10,11,12}};
        int C[][] = new int[ROW][COL];
       
        System.out.printf("陣列A的內容為(3x3)：\n");   
        show(A);
       
        System.out.printf("\n陣列B的內容為(3x3)：\n");   
        show(B);
       
        add(A, B, C);
       
        System.out.printf("\n陣列A+B=C，陣列C的內容為(3x3)：\n");   
        show(C);
    }
    
    public static void add(________________) {
        ...
    }
    
    public static void show(________) {
        ...
    }
}
```
