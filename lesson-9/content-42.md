# 河內塔問題

河內塔是根據一個傳說形成的一個問題：

有三根杆子A，B，C。A桿上有N個(N>1)穿孔圓盤，盤的尺寸由下到上依次變小。要求按下列規則將所有圓盤移至C桿：

1. 每次只能移動一個圓盤；
2. 大盤不能疊在小盤上面。

提示：可將圓盤臨時置於B桿，也可將從A桿移出的圓盤重新移回A桿，但都必須尊循上述兩條規則。

問：如何移？最少要移動多少次？

![河內塔示意動畫][1]

（出處：[維基百科 - 河內塔][2]）


  [1]: http://upload.wikimedia.org/wikipedia/commons/4/4f/Tower_of_Hanoi.gif
  [2]: http://zh.wikipedia.org/zh-tw/%E6%B1%89%E8%AF%BA%E5%A1%94

## 執行結果

```
請輸入盤數：3
盤由 A 移至 C
盤由 A 移至 B
盤由 C 移至 B
盤由 A 移至 C
盤由 B 移至 A
盤由 B 移至 C
盤由 A 移至 C
```

## 程式碼

Hanoi.java

```java
import java.util.*;
import static java.lang.System.out;

public class Hanoi {
    static class Move {
        char from, to;
        Move(char from, char to) {
            this.from = from;
            this.to = to;
        }
    }
	
    List<Move> solve(int n) {
        moves = new ArrayList<Move>();
        move(n, 'A', 'B', 'C');
        return moves;
    }

    private List<Move> moves;
	
    private void move(int n, char a, char b, char c) {
        if(n == 1) {
            moves.add(new Move(a, c));
        } else {
            move(n - 1, a, c, b); 
            move(1, a, b, c); 
            move(n - 1, b, a, c);
        }
    }
    
    public static void main(String args[]) {
        out.print("請輸入盤數：");
        Hanoi hanoi = new Hanoi();
        int n = new Scanner(System.in).nextInt();
        for(Move move : hanoi.solve(n)) {
            out.printf("盤由 %c 移至 %c%n", move.from, move.to);
        }
    }
}
```

## 開始練習

```java
import java.util.*;
import static java.lang.System.out;

public class Hanoi {
    static class Move {
        char from, to;
        Move(char from, char to) {
            this.from = from;
            this.to = to;
        }
    }
	
    List<Move> solve(int n) {
        moves = new ArrayList<Move>();
        move(n, 'A', 'B', 'C');
        return moves;
    }

    private List<Move> moves;
	
    private void move(int n, char a, char b, char c) {
        //請完成遞迴函式設計
    }
    
    public static void main(String args[]) {
        out.print("請輸入盤數：");
        Hanoi hanoi = new Hanoi();
        int n = new Scanner(System.in).nextInt();
        for(Move move : hanoi.solve(n)) {
            out.printf("盤由 %c 移至 %c%n", move.from, move.to);
        }
    }
}```
