# 110. 圓形面積

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 請撰寫三個方法計算下面圖形的面積，然後輸出總面積。 <br/><div style="padding-left:200px"><img src="/content/20/files/graph.png" width="100" alt="" /></div>
2. 假設圓的半徑 = 5，PI = 3.1415926，請寫出 calCircle 函數計算圓面積。 
3. 圓面積計算公式: 半徑平方 * 圓周率（PI）。 
4. 三角形的底 = 10，高 = 5，請寫出 calTriangle 函數計算三角形面積。 
5. 三角形面積計算公式: 底 * 高 / 2。 
6. 假設長方形的長 = 5，寬 = 10，請寫出 calRectangle 函數計算方形面積。 
7. 長方形面積計算公式: 長 * 寬。 
8. 圖形面積 = 圓面積 + 三角形面積 + 長方形面積。 
9. 執行結果顯示如執行結果參考畫面。 

### 執行結果參考畫面 ###

    圓形面積為：78.539815
    三角形面積為：25.000000
    方形面積為：50.000000
    此圖形面積為：153.539815

## 執行結果

```
圓形面積為：78.539815
三角形面積為：25.000000
方形面積為：50.000000
此圖形面積為：153.539815
```

## 程式碼

JPA01.java

```java
import java.util.Scanner;
public class JPA01 {
    public static void main(String args[]) {
        double totalarea;
        System.out.printf("圓形面積為：%f\n", calCircle(5));
        System.out.printf("三角形面積為：%f\n", calTriangle(10, 5));
        System.out.printf("方形面積為：%f\n", calRectangle(5, 10));
        totalarea = calCircle(5) + calTriangle(10, 5) + calRectangle(5, 10);
        System.out.printf("此圖形面積為：%f\n" ,totalarea);
    }
    
    static double calCircle(int x) {
        double area;
        area = x * x * 3.1415926;
        return area;
    }
    
    static double calTriangle(int x, int y) {
        double area;
        area = x * y / 2.0;
        return area;
    }
    
    static double calRectangle(int x, int y) {
        double area;
        area = x * y ;
        return area;
    }
}
```

## 開始練習

```java
import java.util.Scanner;

public class JPD01 {
    public static void main(String args[]) {
        double totalarea;
        System.out.printf("圓形面積為：%f\n", calCircle(5));
        System.out.printf("三角形面積為：%f\n", ________________);
        System.out.printf("方形面積為：%f\n", _______________);
        totalarea = __________________________________________;
        System.out.printf("此圖形面積為：%f\n", totalarea);
    }
    
    _______ ______ calCircle(_____) {
        
    }
    
    ______ ____ calTriangle(_____________) {
        
    }
    
    ______ ____ calRectangle(______________) {
        
    }
}```
