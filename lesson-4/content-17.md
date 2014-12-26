# 107. 運動成績

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 本題使用其他類別定義的類別方法。
2. 假設老師在計算運動成績的分數時，動作佔 1 分，技巧佔 2 分，團隊表現佔 3 分。 
3. basketball 的分數計算方式為：動作 (action) + 技巧 (skill) + 團隊表現 (teamgame)；baseball 的分數計算方式為：10 + 技巧 (skill) + 團隊表現 (teamgame)。 
4. JPD01.java 內已提供 basketball 與 baseball 兩個類別及成績的計算方式，它們各有一個 calGrade 方法，請將此方法於 basketball 與 baseball 兩個類別中補上。 
5. 程式執行時直接計算成績，並輸出 basketball 及 baseball 的成績，顯示如執行結果參考畫面。

### 執行結果參考畫面 ###

    The basketball grade is 6
    The baseball grade is 15

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求。（配分：10分）

## 執行結果

```
The basketball grade is 6
The baseball grade is 15

```

## 程式碼

JPA01.java

```java
public class JPA01 {
    public static void main(String argv[]) {
        int action = 1, skill = 2, excitement = 3;

        System.out.println("The basketball grade is " + Basketball.calGrade(action, skill, excitement));
        System.out.println("The baseball grade is " + Baseball.calGrade(action, skill, excitement));
    }
}

class Basketball {
    public static int calGrade(int a, int s, int e) {
        return a + s + e;
    }
}

class Baseball {
    public static int calGrade(int a, int s, int e) {
        return 10 + s + e;
    }
}

```

## 開始練習

```java
public class JPD01 {
    public static void main(String argv[]) {
        int action = 1, skill = 2, excitement = 3;

        System.out.println("The basketball grade is " + Basketball.calGrade(_____________________));
        System.out.println("The baseball grade is " + _______________(________________________));
    }
}

class Basketball {
    __________________________________ {
        return a + s + e;
    }
}

class Baseball {
    __________________________________ {
        return 10 + s + e;
    }
}```
